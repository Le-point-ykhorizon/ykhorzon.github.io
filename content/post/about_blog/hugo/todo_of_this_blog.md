+++
author = "ykhorizon"
date = "2017-10-08T13:06:07+08:00"
title = "Build my own hugo blog with additional features"
categories = ["blog","blog/hugo"]
topics = []
keywords = []
tags = []
type = "post"
draft = true
+++

# Outline
I'll mainly discuss about two major aspect of using hugo. Part II is based on my personal experience which may not be suitable for other.

- PART I: Wanted Feature (Those important feature for me)
- PART II: Content Management Experience


# Wanted Features (or Solutions)

- [x] 1. Display hierarchy categories (Partial)
- [ ] 2. Search inside blog
- [ ] 3. Manage image in static
- [ ] 4. Shortcut for image url 
- [ ] 5. Access to file by title/filename in multilingual condition
- [ ] 6. Manage tags/catagories/keyword/series 
- [ ] 7. How to hybrid directory(section), category and tag to manage content ?
- [x] 8. Suggestions for writing flow 

Other

- Multilingual
- Table of Content (ToC) 
- [MathJax (New)](https://gohugo.io/tutorials/mathjax/) 
- Discuusion Disqus (__Done__)
- Image and other static resource link and management
- Multi-level menu or categories (hierarchy menu)
- Search blog content
- Template
- [SEO](http://brendan-quinn.xyz/post/working-with-hugos-internal-partial-templates-facebook-and-open-graph/)

# PART I: Wanted Feature

## 1.Display hierarchy categories
The categories of hugo is only one-level (It's called Taxonomies). But I want the categories like the following image. It's very common feature in another static site generator **hexo**
![](/content_img/todo_of_this_blog/1.png)
[image src: blog of morris821028 ](http://morris821028.github.io/)

I had survey some feasible method to fitting my requirement, but I'm still solving this problem.
    

### Method 1
Use a prefix string as main category 
- Implement with simple concatenated category string

Example: 

- blog (Main Category)
- blog/hugo (Sub Category)

![](/content_img/todo_of_this_blog/3.png)

```html
  <!-- Taxonomies (default is tag and categories) -->
  {{ range $key, $value := .Site.Taxonomies }} {{ $len := len $value }} {{ if (not ( eq $len 0 ) ) }}
  <div class="section taxonomies">
    <header>
      <div class="title"><b>{{ $key | humanize }}</b></div>
    </header>

    <div class="content">
      <ul>
        {{ range $value.Alphabetical }}
        <!--  range first 15 $value.ByCount -->
        <li><a href="{{$.LanguagePrefix }}/{{ $key }}/{{ .Name | urlize }}">{{ .Name }} ({{.Count}})</a></li>
        {{ end }}
      </ul>
    </div>
  </div>
  {{ end }} 
  {{ end }}
``` 
You can check out the document [offical: order taxonomies](https://gohugo.io/templates/taxonomy-templates/#order-taxonomies)

__Result__

![](/content_img/todo_of_this_blog/2.png)

More advanced solution, I would like to write a javascript snippets to **convert** flatted categories into hierarchy categories with some category format trick.

### Other Solutions 


- [Solution 1 - hugo-nested-menu-example](https://github.com/vjeantet/hugo-menu-show)
  -  [Demo](http://vjeantet.github.io/hugo-menu-show/)
- [Solution 2 - hugo-tranquilpeak-them](https://github.com/kakawait/hugo-tranquilpeak-theme)
  - [Demo](https://tranquilpeak.kakawait.com/categories/)
- [Solution 3 - section tree](https://github.com/bep/hugotest)
  - [has bug in my theme](http://experiments.wemakesites.net/css3-treeview.html)

Miscellaneous

- [Github Issue Discussion 1](https://github.com/gohugoio/hugo/issues/465)
- [Github Issue Discussion 2](https://github.com/gohugoio/hugo/pull/3309)

## 2.Search inside blog
Wait to explore ...
## 3.Manage image in static
Wait to explore ...
## 4.Shortcut for image url 
Wait to explore ...


# PART II: Content Management Experience


## 5. Access to file by title/filename in multilingual condition
I'm used to write blog by Visual Studio Code, so my procedure likes

1. Start local server in command line (hugo server -w -D)
2. View the blog in browser and find the title of the article which I want to work on
3. Use **search in file** access article by title
4. It's time to get to write!

## 6. Manage tags/catagories/keyword/series 

1. Every article only have one category. It should be the most important characteristic.
2. Category should not equal to tag

## 7. How to hybrid directory(section), category and tag to manage contents ?

## 8. Suggestions for writing flow 

__Keep Atomicity__

- Finish a complete part of article in one writing work and don't let muse fleeing.
- Immediately deploy article after finishing, like developer commit code with git.
