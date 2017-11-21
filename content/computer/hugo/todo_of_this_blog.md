+++
author = "ykhorizon"
date = "2017-10-08T13:06:07+08:00"
title = "Build my own hugo blog with additional features"
categories = ["blog","blog/hugo"]
topics = []
keywords = []
tags = ["undone"]
type = "post"

+++

# Abstract
I'll mainly discuss about two major aspect of using hugo. Part II is based on my personal experience which may not be suitable for other.

- PART I: Wanted Feature (Those important feature for me)
- PART II: [Content Management Experience]()


# Wanted Features (or Solutions)

- [x] 1. Display hierarchy categories (Partial)
- [ ] 2. Search inside blog
- [ ] 3. Manage image in static
- [ ] 4. Shortcut for image url 

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