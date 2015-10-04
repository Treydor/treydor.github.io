---
layout: post
title: Microdata
date: October 4, 2015
blog: true
---

Like [semantic HTML elements]({{ site.baseurl}}/2015/09/29/Semantic-Elements.html), microdata is bot-readable and can allow search engines to do some pretty cool things with our data. This post will walk through an example of how microdata is added to our markup and will also cover how a search engine like Google processes and uses our information.

### Attributes

There are five different microdata attributes, but only a few them are necessary to get us up and running with microdata. The most common attributes are `itemscope`, `itemtype` and `itemprop`.

To create an item with microdata add `itemscope` to our container.

```HTML
<div itemscope></div>
```

We also want to add a vocabulary to our microdata. We can do this by adding the `itemtype` attribute.

One of the most common vocabularies is [Schema.org](http://schema.org). Schema.org is a collaboration of Google, Bing and Yahoo that aims to create a standardized vocabulary for web use. These variables essentially make it possible for a bot to associate meaning to words like Business, Restaurant, Book and Movie. Once the variable becomes semantic, search engines are able to render the microdata in a special way.

For the sake of our example, let's add the Schema.org [Recipe](http://schema.org/Recipe) vocabulary.

```HTML
<div itemscope itemtype="http://schema.org/Recipe"></div>
```

Once you have your vocabulary specified, the next thing we want to do is add properties to our element. These properties give meaning to our data.

To add properties to our newly created item use the `itemprop` attribute.

```HTML
<div itemscope itemtype="http://schema.org/Recipe">
  <h1 itemprop="name"> ... </h1>
  <span itemprop="recipeIngredient"> ... </span>
  <span itemprop="recipeIngredient"> ... </span>
  <span itemprop="recipeIngredient"> ... </span>
</div>
```

So what do all these variables do? Well for one, adding microdata will allow for more eye-catching search results. A search result that stands out and is different from the others can contribute to more clicks which will ultimately increase the website's traffic.

<img class="blog__image--small" src="/assets/images/blog/microdata/microdata.png">

If you ever find yourself using microdata there are plenty of resources to make sure you are highlighting your content effectively. In the case of our recipe, [Google Developers](https://developers.google.com/structured-data/rich-snippets/recipes) displays a variety of examples, and explains the vocabulary attribute very thoroughly.

---

### References
* [Dive Into HTML5 - Microdata](http://diveintohtml5.info/extensibility.html)
* [HTML5 Doctor - Extending HTML5 Microdata](http://html5doctor.com/microdata/)
* [HTML Goodies - HTML5 Microdata](http://www.htmlgoodies.com/html5/Web-Developer-Tutorial-HTML5-Microdata-3920016.htm#fbid=4RysEGf-yCX)
