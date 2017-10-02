---
layout: post
title: Standardized CSS Naming Conventions with BEM
description: What is BEM and how does it improve CSS? How to create and maintain more readable and object oriented CSS through the BEM naming metholodology.
comments: true
tags: tutorials, how-to, learning, code, css 
---
## What is BEM?
BEM is a CSS methodology that aims to make CSS more scalable, reusable and maintainable. The implementation varies which is why it is important to establish standards that your team can agree upon. BEM stands for Block, Element, Modifier and is focused on organizing CSS classes by breaking down a site into blocks. The naming convention used in BEM is hierarchical so understanding those conventions as a team will help optimize the front-end development process. BEM methodology demands specificity and in turn prevents having to use `!important` which is bad practice anyway. This allows other developers working with the code to quickly and easily identify what that code is doing just by looking at its name.

## The BEM Structure
The official BEM naming convention goes as follows:

{% highlight css %}
    .block {}
    .block--modifier {}
    .block__element {}
    .block__element--modifier {}
{% endhighlight %}

While the double underscores and hyphens look a little goofy at first, they actually make sense considering a name could already have more than one word such as `.sign-up`. When using the BEM naming convention, its the double underscores or hyphens that give a visual cue to the relationship of its containing block.

## Blocks
The first step to establishing the BEM structure is to determine what blocks require naming. The block "encapsulates a standalone entity that is meaningful on its own"[1](http://getbem.com/naming/). Blocks are the standalone chunks of code that are modular and house their own set of elements. For example, the header, body, sidebar, footer and content area are all considered blocks and will have elements associated to them. 

The idea of a block is that it should be modular enough that it can be used across the entire site without having to modify the code in any way. For this reason, there are a couple rules to take into consideration:
- Never use an ID to name blocks or elements. The specific nature of the BEM naming convention works best with classes and if ID's are mixed in, it confuses the purpose of the BEM methodology.
- Do not use positioning rules in BEM blocks. This means a block should not contain rules such as `float`, `margin` or `width`.


## Elements and Modifiers
Elements are bits of code that are associated to a block. Each element is written after the block and is connected by two underscores. All elements are working within the context of their assigned block, hence the block designation before the element name.

`.block__element {}`

In a more practical usage, this translates to something like this: `.navbar__tab {}` with `navbar` being the block and `tab` being the element. 

Modifiers, simply stated, modify the state of an existing block or element. If a pre-existing block or element requires an alternate version, a modifier is used to designate that difference. For example, `navbar__tab--active` with `active` modifying the `tab` element.

## Nesting with Sass
Elements can be nested inside each other.
You can have any number of nesting levels.
An element is always part of a block, not another element. This means that element names can't define a hierarchy such as `block__elem1__elem2`.

An example of nesting in a preprocessor:

{% highlight sass %}
.navbar {
   ... rules ....
   &__tab {
      ... rules ....
      &--active {
         ... rules ....
      }
   }
}
{% endhighlight %}

[1]: https://www.jernejsila.com/2016/06/29/css-specificity-fundamental-learn/
[2]: https://en.bem.info/methodology/naming-convention/#element-name
[3]: https://en.bem.info#nesting-1
[4]: https://en.bem.info/methodology/naming-convention/#modifier-name
[5]: https://en.bem.info/methodology/faq/#why-include-the-block-name-in-names-of-modifier-and-element
[6]: https://en.bem.info/methodology/filestructure/#file-structure-organization
[7]: https://en.bem.info/methodology/build/#bem-project-building-methodology
[8]: https://en.bem.info/methodology/filestructure/#nested
[9]: https://github.com/bem-site/bem-method/issues/new
[10]: http://prose.io/#bem-site/bem-method/blob/bem-info-data/method/quick-start/quick-start.en.md