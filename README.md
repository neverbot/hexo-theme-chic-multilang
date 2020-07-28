<h1 align="center"><a href="https://github.com/neverbot/hexo-theme-chic-multilang" target="_blank">Chic Theme, multilang version</a></h1>

This is a modified version of the [Chic Theme](https://github.com/Siricee/hexo-theme-Chic) for [Hexo](https://hexo.io), made by [Siricee](https://github.com/Siricee). **Important**: Multilanguage does not mean the theme interface, Chic was _already_ multilanguage in that sense. It means it supports blog contents written in multiple languages, using the plugin [hexo-multilang](https://github.com/neverbot/hexo-multilang/) made by [neverbot](https://github.com/neverbot). If you need to publish a blog with posts written and translated to multiple languages, this could be used a a solution. As you can see in the screenshot below, you will have a dropdown to select the content language of the blog.

<p align="center">
  <img width="700" alt="chic multilang screenshot" src="/source/image/screenshot.png">
</p>

> Chic, French word meaning 'Elegant' in English.

<p align="center">
<img alt="Author" src="https://img.shields.io/badge/Author-Siricee-lightgray.svg"/>
<img alt="Author" src="https://img.shields.io/badge/Author-neverbot-lightgray.svg"/>
<img alt="Hexo" src="https://img.shields.io/badge/Hexo-3.0+-0e83cd.svg"/>
<img alt="Device" src="https://img.shields.io/badge/Device-responsive-orange.svg"/>
</p>

## Documentation language

- [English](README.md)

## Contents
- [Documentation language](#documentation-language)
- [Contents](#contents)
- [Introduction](#introduction)
- [Demo](#demo)
- [Features](#features)
- [Installation](#installation)
- [Configuration](#configuration)
- [LICENSE](#license)

## Introduction
An elegant, powerful, easy-to-read Hexo theme.

## Demo
- [maldorne.org](https://maldorne.org)

## Features
- Appropriate blank blocks, elegant but not simple.

- Light/Dark theme.

- Abundant highlight mode.

- Elaborately selected fonts, best reading experience. *'Microsoft Jhenghei' especially recommended.*

- Auto fit Mobile and Screen responsively.

- Support MathJax, support formula written in LaTeX.

## Installation

```bash
cd your-blog/
# remove the basic hexo plugins
npm remove hexo-generator-archive hexo-generator-category hexo-generator-index hexo-generator-tag hexo-generator-basic-set hexo-generator-i18n
# install the basic plugin needed
npm install hexo-multilang
# install some extras needed
npm install hexo-fontawesome
```

Change the `language` configuration in your `_config.yml` to the multiple languages you needed, and the `permalink` and `new_post_name` so they include the `:language` slug somewhere:
```yml
language: [en, es]
permalink: :language/:year/:month/:day/:title/
new_post_name: :language/:year/:month/:day/:title.md
```

Copy the `hexo-multilang` configuration to the `_config.yml` file:
```yml
plugins:
  hexo-multilang:
    languages: [en, es]  

    pagination-dir: page

    index-generator:
      per-page: 5
      order-by: -date
      index-dir: 
      default-lang: en

    archive-generator:
      per-page: 10
      order-by: -date
      archives-dir: archives
      yearly: true
      monthly: true
      daily: false

    category-generator:
      per-page: 10
      order-by: -date
      categories-dir: categories
      enable-index-page: true

    tag-generator:
      per-page: 5
      order-by: -date
      tags-dir: tags
      enable-index-page: true
```

Install this theme inside your blog installation directory:
```bash
cd your-blog/themes
git clone https://github.com/neverbot/hexo-theme-chic-multilang.git
# Modify theme setting in _config.yml to hexo-theme-chic-multilang.
```

And last but not least, create some initial content to test the blog:
``` bash
$ hexo new 'Hello world'
INFO  Posts created in: en, es
INFO  Created: /<your path>/source/_posts/es/1900/01/01/hello-world.md
INFO  Created: /<your path>/source/_posts/en/1900/01/01/hello-world.md
```

If you now generate the blog and serve it, should be able to see the new contents:
``` bash
$ hexo generate
$ hexo server
INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```

## Configuration
<details>
<summary><mark>Click here to spread</mark></summary>

```yaml
# Header
navname: Chic Multilang

# navigator items
nav:
  - blog: 
    name: nav.blog 
    url: /archives

# favicons
icons: true

# Profile
avatar: /image/avatar.jpeg

i18n:
  language: [en, es]

# main menu navigation
## link is the complete url
## icon is the fontawesome icon name
## prefix is the fontawesome style
## Unused keys can be commented out.
links:
  Blog: 
    link: /archives
    icon: book-open
    prefix: fas
  Twitter: 
    link: https://twitter.com/neverbot
    icon: twitter
    prefix: fab
  LinkedIn: 
    link: https://www.linkedin.com/in/ivanalonso
    icon: linkedin
    prefix: fab
  Github: 
    link: https://github.com/neverbot/
    icon: github
    prefix: fab
#  Category:
#  Tags: 
#  Link:
#  Resume:
#  Publish:
#  Trophy:
#  Gallary:
#  RSS:
#  AliPay:
#  ZhiHu: 
#  FaceBook:
#  Skype:
#  CodeSandBox:
#  CodePen:
#  Sketch:
#  Gitlab:
#  Dribble:
#  Instagram:
#  Reddit:
#  YouTube:
#  QQ:
#  Weibo:
#  WeChat:

# how links show: you have 2 choice--text or icon.
links_text_enable: false
links_icon_enable: true

# Post page
## Post_meta
post_meta_enable: true

post_author_enable: true
post_date_enable: true
post_category_enable: true
## Post copyright
post_copyright_enable: true

post_copyright_author_enable: true
post_copyright_permalink_enable: true
post_copyright_license_enable: false
post_copyright_license_text: Copyright (c) 2020 neverbot
post_copyright_slogan_enable: false

## toc
post_toc_enable: true
page_toc_enable: true

# Page
page_title_enable: true

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: MMMM D, YYYY
time_format: HH:mm:ss

# stylesheets loaded in the <head>
stylesheets:
  - /css/style.css

# scripts loaded in the end of the body
scripts:
  - /js/script.js
  - /js/tocbot.min.js
    # tscanlin/tocbot: Build a table of contents from headings in an HTML document.
    # https://github.com/tscanlin/tocbot

# plugin functions
## Mathjax: Math Formula Support
## https://www.mathjax.org
mathjax:
  enable: true
  import: demand # global or demand
  ## global: all pages will load mathjax,this will degrade performance and some grammers may be parsed wrong.
  ## demand: Recommend option,if your post need fomula, you can declare 'mathjax: true' in Front-matter
```
</details>
<br>

**From here the documentation would be the same as in the original theme, so [you should check there](https://github.com/Siricee/hexo-theme-Chic/blob/master/README.md), just in case.**

## LICENSE
Chic © [@Siricee](https://github.com/Siricee)

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
