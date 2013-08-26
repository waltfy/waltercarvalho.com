---
layout: post
title: In The Name of Responsiveness
---

First of all I'm kind of a newbie on this, so take it easy on me will you?

I'm currently working on a project, designing and implementing a web site for a company located in Brazil, Moenda, a traditional "restaurant/cafe" type thing, specialised in Sugar-Cane Juice. Fairly simple project.

Right, so I needed this: a gallery for a responsive website, that looked great and was functional.

I had a look through some websites and really liked what I saw at buffer.com/extras—a simple and elegant solution, without the clutter that we normally see.

So I got out my sketch pad!



Here's what I came up with at first: [Screen Recording of first version.](http://f.cl.ly/items/2a1M3R3t3t3r3U24231o/Screen%20Recording.mov)

As you can see in the video, it had somewhat of responsiveness with the use of media queries, but the images weren't actually resizing fluidly but rather adapting to the screen size with the use of media queries. Problem was, setting a height as a percentage doesn't work as well as the "width" property on CSS (e.g. width: 50% of a parent div, will always be: child div's width = 0.5 * parent div), height doesn't work as well as that, it should, but it just doesn't... I won't even go into how HTML, CSS and JavaScript are kinda of broken and "weird" in many ways.

So I had 2 divs, one containing a background image to a "fixed" width of a percentage (making it responsive) and the other with the same width containing some information (text) about that image inside another div, as you hovered the image I wanted the second div (the one with the info) to "slide" up and as your cursor left the image, it'd go back down with a nice CSS transition.

First problem I encountered: how to hover an element and change the properties of another... this to me was kind of a never needed property before—I was actually very surprised by this—but with the use of some magic (Google) I found on my beloved StackOverflow the following:

Affecting an element while hovering another:

If child div is inside the parent:
#parent:hover > #child { /* style */ };

If child div is next to (after closing tag) the parent:
#parent:hover + #child { /* style */ };

If child div is somewhere inside the parent:
#parent:hover #child { /* style */ };

Unfortunately I don't record the question, nor could I find it on my history.

Now to make it responsive! I decided to use a workaround with JavaScript which was really "simple", but sometimes to see the simple it's really, quite hard. I went on to write a really simple function that got the width of the containing div and setting it as both of the divs height (as I wanted it to be a square) and setting a time for it to call itself again which makes it read the width and set it as the height almost instantly, so if there was a change on its already responsive width, that, would affect it's height. I haven't seen many cases of using a responsive "height" for a div, and I think it's pretty awful that I couldn't use height: 100%; anyways...

And here's the [final result](http://www.waltercarvalho.com/gallery): a pretty responsive gallery, which looks pretty slick and works great.

Of course the 100ms time may be a little too frequent and there is still a lot of tweaking to be done, however I still think it's a pretty neat way of displaying a set of images.

Hope you enjoyed it, see'ya!