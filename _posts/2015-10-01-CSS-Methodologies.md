---
layout: post
title: Methodologies
date: October 1, 2015
blog: true
---

There is a great deal of debate over the process of naming your classes. What works for somebody, may not work for you and that is totally fine. These methodologies serve as a framework to better organize our HTML and CSS. They can be taken literally or in combination with one another.

### Object Oriented CSS

Object Oriented CSS (OOCSS) focuses on reusable classes that are not only scalable, but also easy to maintain. OOCSS adheres to two main principles.

The first principle of OOCSS aims at keeping structural properties separate from visual properties. The example below is what an element may look like if the developer is not adhering to OOCSS principles.

```css
.rectangle {
  background: #ddd;
  border: 1px solid #ccc;
  height: 40px;
  width: 300px;
}
```

After applying OOCSS principles, our new element would look something like this:

```css
.rectangle {
  height: 40px;
  width: 300px;
}

.inactive {
  background: #eee;
  border: 1px solid #ddd;
}
```

Separating the structural properties from the visual properties gives us standalone classes that are completely modular and can be applied to any element.

The second principle talks about keeping the content separate from the container. Below is an example that is not using OOCSS.

```css
.footer h2 {
  color: orange;
  font-size: 2em;
  text-transform: uppercase;
}
```

The problem with this particular element is that it is not reusable. We are being too specific and limiting our style to just the `<h2>` elements in our `<footer>`. What if we wanted to apply a style to a `<h2>` located somewhere else on our website? One option is to create another class, but then we would just be duplicating code.

One of things I really like about OOCSS is that it forces us to think about our code in a reusable way. Instead of targeting the `<h2>` specifically in the `<footer>`, think about applying a base style to the `<h2>` and adding `.special` to modify the style.

```css
h2 { font-size: 2em; }

.special {
  color: orange;
  text-transform: uppercase;
}
```

### Scalable and Modular Architecture for CSS

Scalable and Modular Architecture for CSS (SMACSS) creates CSS rules and categorizes them in five different ways. The categories are Base, Layout, Module, State and Theme.

* Base rules are the default styles.

* Layout rules divide the page in to sections and hold one or more elements together.

* Modules are the reusable, modular parts of the design.

* State rules describe how a particular element will look in a particular state.

* Theme rules describe how modules and layouts might look.

The purpose of the different categories is to allow for better organization. The creator of SMACSS, [Jonathan Snook](http://snook.ca/), also recommends adding prefixes to class names. The prefixes attached to classes directly correlate to their specified rule category.

> I like to use a prefix to differentiate between Layout, State, and Module rules. For Layout, I use l- but layout- would work just as well. Using prefixes like grid- also provide enough clarity to separate layout styles from other styles.
<sup>
  [[2]](https://smacss.com/book/categorizing)
</sup>

The author adds thats that this particular methodology should not be interpreted as a rigid framework, but instead more as a style guide to help us better organize our CSS.

### Block, Element, Modifier (BEM)

The third and final methodology I'll talk about is Block, Element, Modifier or BEM.

Although the BEM code may not scream visually appealing, there is a certain simplicity to this methodology that makes organizing our CSS easy.

```css
.project-list { ... }
.project-list__card { ... }
.project-list__card--large { ... }
```

The BEM methodology starts with a block, which is essentially the top level of our element. In this case our block-lvel is `.project-list`.

The next level of BEM is element. The element level are child elements of our block level. In this case `project-list__card` is the element level. Within BEM the element level is usually denoted by two underscores followed by the block or element name.

The last part of our BEM element is the modifier. Modifiers are written by  appending two hyphens to the name of the block. In our example, our modifier is `project-list__card--large`. Modifiers are modular in the sense that you can use them as you need.

At first I was really turned off by the large class names associated with BEM. I asked myself why I needed a class called `.project-list__card--large` when instead I could just use `.card-big` and achieve the same thing. As I began to work in larger projects I was increasingly pushing myself to create cleaner and more reusable code. BEM, as an organizational tool, just seemed natural because of how literal it is. I think BEM really shines in larger projects, where there is a variety of people working on the same code.

Within the next few days I hope to publish a new blog entry about Microdata, stay tuned!

---

### References
1. [AppendTo - What is OOCSS?](http://appendto.com/2014/04/oocss/)
2. [Scalable and Modular Architecture for CSS](https://smacss.com/)
3. [CSS Tricks - BEM 101](https://css-tricks.com/bem-101/)
