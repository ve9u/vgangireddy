---
title: Checkpoints for MySQL security
date: 2021-11-14T03:10:36+00:00
language: en
featured_image: "../assets/images/featured/featured-img-placeholder.png"
summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed cursus, odio
  nec venenatis lacinia, lacus lectus varius nisi, in tristique mi purus ut libero.
description: ''
author: Venu Gangireddy
authorimage: "../assets/images/global/author.webp"
categories: blog
tags:
- blog
- MySQL
- Security
draft: true

---
**Advertisement :smile:**

* [**pica**](https://nodeca.github.io/pica/demo/) - high quality and fast image
  resize in browser.
* [**babelfish**](https://github.com/nodeca/babelfish/) - developer friendly
  i18n with plurals support and easy syntax.

You will like those projects!

***

# OS Security

## SELinux

## Auditd

## 2FA

## IPTables Firewall

## Limit Sudoers

## Up-to-date 

## Don't run MySQL as root user, unnecessary file access from MySQL

### MySQLD accessble by only mysql user

# Application Security

## Sanitize your inputs (SQL injections)

## DO NOT ignore MySQL warnings

## Never give all privileges to application users

## Sanitize the inputs:

### Validate Configuration Files / Tables

### User assertions abort

# MySQL Authentication

## Local : 

### caching _ sha2 _ password

### DNS resolve

### Password Expiration

Indented code

    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code

Block code "fences"

    Sample text here...

Syntax highlighting

``` js
var foo = function (bar) {
  return bar++;
};

console.log(foo(5));
```

## Tables

| Option | Description |
| --- | --- |
| data | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext | extension to be used for dest files. |

Right aligned columns

| Option | Description |
| ---: | ---: |
| data | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext | extension to be used for dest files. |

## Links

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)

## Images

![Minion](https://octodex.github.com/images/minion.png)
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text](https://octodex.github.com/images/dojocat.jpg "The Dojocat")

With a reference later in the document defining the URL location:

## Plugins

The killer feature of `markdown-it` is very effective support of
[syntax plugins](https://www.npmjs.org/browse/keyword/markdown-it-plugin).

### [Emojies](https://github.com/markdown-it/markdown-it-emoji)

> Classic markup: :wink: :crush: :cry: :tear: :laughing: :yum:
>
> Shortcuts (emoticons): :-) :-( 8-) ;)

see [how to change output](https://github.com/markdown-it/markdown-it-emoji#change-output) with twemoji.

### [Subscript](https://github.com/markdown-it/markdown-it-sub) / [Superscript](https://github.com/markdown-it/markdown-it-sup)

* 19^th^
* H\~2\~O

### [<ins>](https://github.com/markdown-it/markdown-it-ins)

\++Inserted text++

### [<mark>](https://github.com/markdown-it/markdown-it-mark)

==Marked text==

### [Footnotes](https://github.com/markdown-it/markdown-it-footnote)

Footnote 1 link\[^first\].

Footnote 2 link\[^second\].

Inline footnote^\[Text of inline footnote\] definition.

Duplicated footnote reference\[^second\].

\[^first\]: Footnote **can have markup**

    and multiple paragraphs.

\[^second\]: Footnote text.

### [Definition lists](https://github.com/markdown-it/markdown-it-deflist)

Term 1

:   Definition 1
with lazy continuation.

Term 2 with _inline markup_

:   Definition 2

        { some code, part of Definition 2 }
    
    Third paragraph of definition 2.

_Compact style:_

Term 1
\~ Definition 1

Term 2
\~ Definition 2a
\~ Definition 2b

### [Abbreviations](https://github.com/markdown-it/markdown-it-abbr)

This is HTML abbreviation example.

It converts "HTML", but keep intact partial entries like "xxxHTMLyyy" and so on.

\*\[HTML\]: Hyper Text Markup Language

### [Custom containers](https://github.com/markdown-it/markdown-it-container)

::: warning
_here be dragons_
:::