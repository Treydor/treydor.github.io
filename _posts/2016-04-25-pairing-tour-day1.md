---
layout: post
name: Noah Rogers
title: "Pairing Tour: Day 1"
date: April 25, 2016
blog: true
---

This week I started my pairing tour. Today I had the opportunity to pair with Diana, a craftsperson at 8th Light. She is part of the studio maintenance team and is working on a new application for a client.

The first few hours of the day started with me asking questions trying to get more familiar with the app. Diana was great and very knowledgeable about the project, she was able to answer my questions. Once I felt like I was up to speed we began to spike out the design.

After updating our markup and implementing a few basic styles we began to tackle our project's architecture. Typically, I like to follow something that looks like this:

<pre>
stylesheets/
|
| _main.scss                # Primary sass file
| _settings.scss            # Variables
|
|– partials/              
|   |– _buttons.scss        # Button
|   |– _layout.scss         # Layout
|   |– _typography.scss     # Typography rules
|   ...                     
|
|– vendor/
|   |– _colorpicker.scss    
|   |– _font-awesome.scss  
|   ...                  
</pre>

Although we only had a few hours to work together on the project I felt like the day went really well. My goal for the day was to establish a project base that could easily be scaled going forward. Even though we did not complete the entire project, I felt like we left off in a good spot that the person who works on it next can pick up where we left off.
