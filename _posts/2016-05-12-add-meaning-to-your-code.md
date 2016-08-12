---
layout: post
name: Noah Rogers
title: "Add meaning to your code"
date: May 12, 2016
blog: true
---

The importance of a solid structural hierarchy and semantic elements cannot be understated. Semantic elements bring meaning to our markup in a way non-semantic HTML cannot. Let’s dig into this a bit more and find out what it truly means to be semantic.

### Semantic HTML elements
Something is semantic when it relates to it’s meaning. Semantics help humans interpret context by associating meaning with words or phrases. The idea behind semantic HTML elements is very much the same and extends to provide context to computers.

Before we fully dive into semantic elements, I want to stress that there are many non-semantic elements that still have their place in HTML. Take the `<div>` tag, for example. The introduction of the `<section>` element with HTML5 is not a an invitation to replace all of the the `<div>` tags throughout our website. Instead, semantic elements should be used in a sensible manner. Consider the following example:

{% highlight html %}
<div class="navigation"> ... </div>
  <div class="section">
    <div class="section-title">Title</div>
    <div class="description">Description.</div>
  </div>
<div class="footer"> ... </div>
{% endhighlight %}

A human may look at this bit of code and be able to make some assumptions about it. From our CSS classes, we can see that the top-most `<div>` is a navigation of some sort, while the bottom-most `<div>` is a footer. We may associate meaning from our CSS class names or simply by reading the content within our HTML. Unfortunately, a computer does not have the same ability we do. Let’s apply semantic elements and see the difference:

{% highlight html %}
<nav> ... </nav>
  ￼<section>
    <h1>Title</h1>
    <p>Description</p>
  </section>
<footer> ... </footer>
{% endhighlight %}

Class names aside, the addition of semantic HTML elements allows humans and computers alike to contextualize our code. The above example becomes semantic because we properly apply meaning in a way that both humans and computers can understand.

### Semantic elements give power to assistive technologies
Assistive technologies like screen readers also leverage our semantic HTML.

> “Screen readers are audio interfaces. Rather than displaying web content visually for users in a "window" or screen on the monitor, screen readers convert text into synthesized speech so that users can listen to the content.”
>
> -- [WebAIM](http://www.webaim.org/techniques/screenreader)
​

Screen readers are an essential tool for millions of people worldwide who are visually impaired. The addition of semantic elements within our example allows screen reading software to better identify elements within our HTML. Instead of an entire webpage full of `<div>` elements, we have structured our code in such a way that we have easily recognizable elements with meanings attached to them.

Much like visual skimming, we look at headings or keywords to determine if the corresponding information is relevant and something we want to read. Screen readers are no different. A user operating a screen reader can skip between headings, sections or links, limiting the amount of time it may take them to find what they are interested in. This is especially important to remember when styling that `<div>` to look like a heading. We should do our best to treat each of our elements like they are part of our structure.

### An introduction to microdata
￼Microdata is a semantic syntax that allows us to define groups of name:value pairs, ultimately allowing us to apply additional semantics to our HTML. Microdata relies on custom vocabularies to contextualize our code:

> “Think of ‘the set of all HTML5 elements’ as one vocabulary. This vocabulary includes elements to represent a section or an article, but it doesn’t include elements to represent a person or a event.”
>
> -- [Dive Into HTML5](http://www.diveintohtml5.info/extensibility.html)

Microdata allows us to represent different items and then create unique properties used to describe each item. Although we are able to create our very own, there are many established vocabularies that are completely free to use and compatible with major search engines like Google, Bing and Yahoo.

One of the web’s most common microdata vocabularies is Schema.org. Schema.org helps search engines better understand the content within our web pages, ultimately providing richer search results. Let’s take a look at a few of the important global microdata attributes and how they relate to Schema.org:

The `<itemtype>` defines our vocabulary and specifies what our section is about. An `<itemtype>` links to our vocabulary. For the sake of this example we will link to the Recipe schema.

{% highlight html %}
<section itemtype="h​ttp://schema.org/Recipe"​> ... </section>
{% endhighlight %}

The `<itemscope>` attribute should be added to the outermost element in which we are going to apply other attributes to. Using this attribute essentially tells the browser that everything between the defined tag and it’s closing tag is related and within the scope of the `<itemtype>`.

{% highlight html %}
<section itemscope itemtype="h​ttp://schema.org/Recipe"​> ... </section>
{% endhighlight %}

The last major attribute is `<itemprop>`. `<itemprop>` defines information that relates to our `<itemtype>`.
￼￼￼
{% highlight html %}
￼<section itemscope itemtype="http://schema.org/Recipe">
  <h1 itemprop="name">Apple pie</h1>
  <p itemprop="recipeCategory">Desserts</p>
  <ul>
    <li itemprop="recipeIngredient">3-4 medium apples</li>
    <li itemprop="recipeIngredient">1 cup sugar</li>
    <li itemprop="recipeIngredient">1⁄4 teaspoon nutmeg</li>
    <li itemprop="recipeIngredient">1⁄2 stick unsalted butter</li>
    <li itemprop="recipeIngredient">2 store-bought pie crusts</li>
  </ul>
</section>
{% endhighlight %}

In the example above, an `<itemtype>` of recipe is applied. The `<itemtype>` defines our vocabulary and our schema. We then add defined `<itemprop>` tags that relate to the recipe. The scope of our vocabulary will not go beyond the element that contains our `<itemscope>`. Our reward is that a search engines like Google now now understand what our content is about. Our code will now yield better search results!

### Conclusion
In the end, a structured semantic hierarchy helps us easily add context to our code. Semantic markup not only gives us a clear sense of what our content is about, but also makes it possible for search engines, web browsers and assistive technologies like screen readers to more accurately parse our code. Microdata vocabularies like Schema.org enable us with another option to enhance computer readability of our content. With microdata, we are able create more eye-catching search results in the form of rich snippets. Together, these tools ensure that the context of our code will be better understood by both humans and computers alike.

---

### References
* [Dive in to HTML5 - Extensibility](http://diveintohtml5.info/extensibility.html)
* [Dive in to HTML5 - Semantics](http://diveintohtml5.info/semantics.html)
* [National Federation of the Blind](https://nfb.org/blindness-statistics)
* [Schema.org](https://schema.org/)
* [WebAIM](http://webaim.org/techniques/screenreader/)
