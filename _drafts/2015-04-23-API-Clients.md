---
layout: post
title: API Clients
---

I've recently been needing to connect my side projects to some sort of external web service for data, whether it's a server I create or something like Instagram. My first attempt at this was in my Photo Booth app[^1], where I created a small RESTful api server to handle photo processing. 

The gist of this server was to accept POST request for photos from a client running a simple python script, resize the image, load the photo onto S3 and get back the URLs for the full size and thumbnail images. I used this simple API to get the event items needed inside of  my `UITableViewController`and for the event's images inside of my `UICollectionViewController`. As this was my first time writing networking code, I shudder thinking of how bad it is. Caching? Nope. Networking logic inside of `ViewDidLoad` and `CellForItemAtIndexPath`? Sure!  My goal was to get the photos to actually work, as I had never attempted anything of the sort before.

#My next foray into networking was with [Bible Reader] (https://itunes.apple.com/us/app/id851934696?mt=8); I wanted to replace the pre-loaded SQLite database of the King James Version of the Bible with the numerous translations offered by the [Bibles.org](http://tools.bibles.org/api.html) API. This time, I started by reading about best practices for creating an API client, moving all the networking code in a  


[^1]: I _really_ should clean up this app's code and throw it up on GitHub. A shame to spend time on something and never show it to anyone, despite how _*horrible*_ the code is!