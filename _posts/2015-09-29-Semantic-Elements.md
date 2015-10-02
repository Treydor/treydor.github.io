---
layout: post
title: Semantic Elements
date: September 29, 2015
blog: true
---

Semantic is a a word I have heard thrown around a lot since I picked up coding, but what exactly does it mean and how is it related to our field? What is semantic, as it pertains to HTML and CSS, is a popular topic because there is some disagreement on the subject. Most people agree that something is semantic when it's name reflects or helps describe it's purpose.

> Semantics within HTML is the practice of giving content on the page meaning and structure by using the proper element.

Semantics can be broken down in to two areas. The first area deals with actual, semantic HTML elements, the second deals with the naming process and creating class names. Both areas are important, but different.

### Keeping us organized
HTML has numerous semantic tags and with the introduction of HTML5 even more have been added. Basically, a semantic element describes it's meaning to both the browser and the developer.

There are quite a few semantic elements that were added along with HTML5. Here is a list of most of them:

* article
* aside
* details
* figcaption
* figure
* footer
* header
* main
* mark
* nav
* section
* summary
* time

Although these elements differ in name and how they are used, they all have one thing in common: they are HTML5 semantic elements. Some are used more than others, but they all shed a little light on their meaning and purpose by their name alone.

```html
<div class="header">
  <a class="logo">Logo</a>
  <div class="navigation">Navigation</div>
</div>
```

```html
<header>
  <a class="logo">Logo</a>
  <nav>Navigation</nav>
</header>
```

This is a pretty simple situation of how semantic elements can be used. Instead of using numerous `<div>` elements and a variety of classes we can simply use semantic elements like `<header>` and `<nav>`, keeping our code nice and clean.

### Additional functionality
Remember how semantic elements also communicate their meaning to the browser? Not only do these elements provide another level organization for us, they also make our content more accessible to a greater number of devices and users.

Semantic elements interact with things like web crawlers and screen readers, providing an increased functionality. Since these elements are understood by the browser and already have a meaning associated with them, the browser can easily identify them (assuming we're using them correctly). For example, an `<h1>` gives users an ability to skim content via a screen reader by reading each of the headings aloud. Remember, machines are smart, but they cannot infer the meaning we associate to our classes based of their name alone.

In my next blog post I'll continue my discussion about semantics with class names and various CSS methodologies. Make sure to look for it in a few days!

---

### References
* [Dive Into HTML5 - Semantics](http://diveintohtml5.info/semantics.html)
* [HTML5 Doctor - Let's Talk about Semantics](http://html5doctor.com/lets-talk-about-semantics/)
* [Shay Howe - Getting to know HTML](http://learn.shayhowe.com/html-css/getting-to-know-html/)
