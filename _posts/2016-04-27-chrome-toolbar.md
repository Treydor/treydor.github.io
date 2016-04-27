---
layout: post
name: Noah Rogers
title: "theme-color meta tag"
date: April 27, 2016
blog: true
---

Lately I have noticed that the chrome address bar on some websites has been re-colored. It isn't the normal grey color that you would expect. I was immediately intrigued and wanted to find out more.

Well it turns out that a new version of Chrome was released for Android's Lollipop and it gives developers the ability to recolor the default chrome address bar. It turns out it's pretty simple to change as well. The only thing we really need to do is add a meta tag to the `head` of our document, cool huh?

For example, I added `meta name="theme-color" content="#3e5688"` to my my personal website. This changes the color of the address bar to a dark blue.

If you don't have an android phone don't worry, I posted a few photos below. Basically, the screenshot of GitHub is the default behavior that you would expect when visiting websites. The screenshot of my personal blog has a specified theme color.

<div class="blog__image blog__image--side-by-side">
  <img src="/assets/images/blog/theme-color/theme-default.png">
  <img src="/assets/images/blog/theme-color/theme-custom.png">
</div>

So far it looks like it's only supported on Android phones that run Lollipop. Check out [Google Developers](https://developers.google.com/web/updates/2014/11/Support-for-theme-color-in-Chrome-39-for-Android?hl=en) for more information!
