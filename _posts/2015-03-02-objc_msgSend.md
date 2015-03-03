---
layout: post
title: objc_msgSend
---
When I first started reading about Objective-C, one of the more interesting (and confusing!) parts was the concept of message sending vs. method calling. My first experience with an object-oriented language was Java, with it's more standard approach of called methods via [lookup tables](https://en.wikipedia.org/wiki/Lookup_table). 

I previously had a general sense of what message sending was doing in comparison to a lookup table, but this example really cleared things up for me:

When we send an object in Objective-C, 

{% highlight objective-c %}
[foo addObject:bar];
{% endhighlight %}

we are really instructing `foo` to look for a designated selector, which is associated with a number, such as 12.

{% highlight objective-c %}
objc_msgSend(foo, 12, bar);”
{% endhighlight %}

Since `foo` in this case has an `isa` pointer to it's super's class, the super will look for the designated selector if `foo` declares no such selector. That is the beauty of this language; by not requiring the method to be declared by the class at compile time, we can dynamically generate a need portion after compilation. 

Unfortunately, with great power comes great responsibility **and** I still don't really know what I'm doing. I don't know _how_  the dynamic nature could be used to my benefit yet, but I'm excited to learn!