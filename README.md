<h1 align="center"><a href="https://github.com/neverbot/hexo-theme-chic-multilang" target="_blank">Chic Theme, multilang version</a></h1>

This is a modified version of the [Chic Theme](https://github.com/Siricee/hexo-theme-Chic) for [Hexo](https://hexo.io), made by [Siricee](https://github.com/Siricee). **Important**: Multilanguage does not mean the theme interface, Chic was _already_ multilanguage in that sense. It means it supports blog contents written in multiple languages, using the plugin [hexo-multilang](https://github.com/neverbot/hexo-multilang/) made by [neverbot](https://github.com/neverbot). If you need to publish a blog with posts written and translated to multiple languages, this could be used a a solution.

<p align="center">
<img src="https://i.loli.net/2019/06/12/5d006bd289aa325037.png" alt="Chic theme">
</p>

> Chic, French word meaning 'Elegant' in English.

<p align="center">
<img alt="Author" src="https://img.shields.io/badge/Author-Siricee-lightgray.svg"/>
<img alt="Author" src="https://img.shields.io/badge/Author-neverbot-lightgray.svg"/>
<img alt="Node" src="https://img.shields.io/badge/Node-6.0%2B-43853d.svg"/>
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
  - [Add 'Tag', 'Category' Page](#add-tagcategory-page)
  - [MathJax (Render LaTeX Formula)](#mathjax-render-latex-formula)
  - [Image-title](#image-title)
- [Customize](#customize)
- [FAQ](#faq)
- [Gallary](#gallary)
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

**From here the documentation would be the same as in the original theme, so you should check there, just in case.**

### Add 'Tag', 'Category' Page

There is no 'tag' or 'category' page in the site as it initializes. If you need it, please follow the steps below.

1. execute commands
```bash
hexo new page tag
hexo new page category
```
2. enter the dictionary
```bash
cd source/tag
```
3. add 'layout' key
```yaml
// source\tag\index.md
---
title: Tag
layout: tag
---
```
4. Do so with the category page with `Category` as title and `category` as layout.

### MathJax (Render LaTeX formula)

Related config file (`hexo-theme-chic-multilang/_config.yml`):
```yaml
# plugin functions
## Mathjax: Math Formula Support
## https://www.mathjax.org
mathjax:
  enable: true
  import: global # global or demand
  ## global: all pages will load mathjax,this will degrade performance and some grammers may be parsed wrong.
  ## demand: if your post need fomula, you can declare 'mathjax: true' in Front-matter
```
`mathjax` uses the keywords below:
- `enable`: value `true` enables mathjax (default value `true`); value `false` disables it.
- `import`: this key sets mathjax load method, options can be `global` or `demand`.
  - `global`: global import, all pages will load script. It's convenient, but **it may cause some MarkDown grammars to be parsed wrong**. For example, consecutive `$$` will be rendered as a formula; Besides, global import will waste performance in pages without any formula.
  - `demand`: [Recommended] Import mathjax when you need it. After you set this value, if you need to use formula, just declare it in the post Front-matter. Here is an example:
    ```yaml
    ---
    title: MathJax Test
    date: 2019-07-05 21:27:59
    tags:
    mathjax: true # add this statement, MathJax will be enabled in this post.
    ---
    ```
LaTeX grammars will not be illustrated in this doc. In Chic theme, single '$' rounded statement is regarded as inline formula like `$f(x)=ax+b$`; double '$' rounded statement is regarded as block formula like `$$f(x)=ax+b$$`. More information please read LaTeX doc and [Formula test page in Demo Site](https://siricee.github.io/hexo-theme-Chic/2019/07/05/MathJax_test/).

### Image-title

You have 2 methods to import images in your posts:
 
 - image import with GFM (without image-title)
   ```
   ![pic](picUrl)
   ```
 - hexo built-in image tag (with image-title)
   ```
   {% img [class names] /path/to/image [width] [height] '"alt text" "title text"' %}
   ```
So if you want to import as fast as possible, you can use GFM, and this way will also get the best adaptability. 

**If you want to display image-title, you should use hexo built-in image tag.**
- `"alt text"` is used when the image doesn't load or something went wrong in that image (404).
- `"title text"` **will be displayed below the image.**

You can preview image-title and sample code in [Demo site](https://siricee.github.io/hexo-theme-Chic/2019/06/05/markdown_test/#Image)

## Customize

- Highlight Style: Enter `hexo-theme-chic-multilang\source\css\style.styl` change stylesheet with key word `_highlight` in link in `_highlight` dictionary.

- Customize stylesheets in this [stylus](https://stylus-lang.com/) file:

   `hexo-theme-chic-multilang\source\css\custom.styl`

- Customize javascripts in the dictionary:

  `hexo-theme-chic-multilang\source\js`

  Then add declaration in `_config.yml`using the keyword 'script'.

## FAQ

1. I deployed my site on a second-level url (such as username.github.io/blog), and my css, avatar and other sources are missing (404 error)

    Answer: You need to change some URLs in root config keyword. For instance:
    ```yaml
    # (blog/_config.yml)

    # URL
    ## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
    url: https://siricee.github.io/hexo-theme-Chic/  # this is your deploy url.
    root: /hexo-theme-chic-multilang/  # this is your root folder url.
    permalink: :year/:month/:day/:title/
    permalink_defaults:
    ```

2. How to set the dark theme as default for whole site automatically?
   
   Answer: You need to change some code in `hexo-theme-chic-multilang\source\js\script.js`, function `document.ready` as shown below.
   ```javascript
   document.ready(
    function () {
        // ...Omit part of the code
        const isDark = currentTheme === 'dark';
        // change this line to
        // const isDark = currentTheme !== 'dark';
   ```
   Now, you have already set the dark theme as default successfully.

3. More questions will be added...

## Gallery
![screely-1560228577821.png](https://i.loli.net/2019/06/12/5d00a0850285252790.png)
![screely-1560228791041.png](https://i.loli.net/2019/06/12/5d00a0856063661133.png)
![screely-1560228621288.png](https://i.loli.net/2019/06/12/5d00a084e29cd40271.png)
![screely-1560228761180.png](https://i.loli.net/2019/06/12/5d00a0855d28072392.png)

![smartmockups_jwrd4ru3.png](https://i.loli.net/2019/06/12/5d00a085d115d16700.png)

![smartmockups_jwrd9y4r.png](https://i.loli.net/2019/06/12/5d00a085ec26284832.png)

## LICENSE
Chic © [@Sirice](https://github.com/Siricee)

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
