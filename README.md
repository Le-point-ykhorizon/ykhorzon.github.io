# My Tech Blog




All the solutions of 2. 3. are in [offical web - Tools](https://gohugo.io/tools/). But I need to integrate them.

# Quick reminder for Development/Maintainence

Where is javascript and Page Header
- theme/layout/partials/base/metas.html
- theme/layout/partials/base/imports.html
- theme/layout/partials/base/scripts.html


# Abstract
I'll mainly discuss about two major aspect of using hugo. Part II is based on my personal experience which may not be suitable for other.

- PART I: Todo list of function (Those important feature for me)
- PART II: Content Management Experience


# Todo List of function (wait to prioritize)

- [x] Display hierarchy categories (Partial)
- [ ] Search inside blog
- [ ] Manage image in static
- [ ] Shortcut for image url 
- [ ] Access to file by title/filename in multilingual condition
- [ ] Manage tags/catagories/keyword/series 
- [ ] How to hybrid directory(section), category and tag to manage content ?
- [x] Suggestions for writing flow 
- [ ] Multi-language content management

Other

- [ ] drop-down nav bar for sub-directory
- [ ] RSS
- [ ] Table of Content (ToC) 
- [MathJax (New)](https://gohugo.io/tutorials/mathjax/) 
- [x] Discuusion Disqus (__Done__)
- [SEO](http://brendan-quinn.xyz/post/working-with-hugos-internal-partial-templates-facebook-and-open-graph/)

## UI and Appearance 
- Porting this [hexo-theme-beantech](https://github.com/YenYuHsuan/hexo-theme-beantech) to hugo
- hidden sidebar
- article header line font 


# PART I: Wanted Feature

## Display hierarchy categories (main-category and sub-category)

### Requirement
The categories of hugo is only one-level (It's called Taxonomies). But I want the categories like the following image. It's very common feature in another static site generator **hexo**

![](https://raw.githubusercontent.com/ykhorzon/ykhorzon.github.io.soruce/master/static/content_img/todo_of_this_blog/1.png)
[image src: blog of morris821028 ](http://morris821028.github.io/)

    
### Implementation Idea
1. Hugo natively support function to generate category

![](https://raw.githubusercontent.com/ykhorzon/ykhorzon.github.io.soruce/master/static/content_img/todo_of_this_blog/3.png)

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

![](https://raw.githubusercontent.com/ykhorzon/ykhorzon.github.io.soruce/master/static/content_img/todo_of_this_blog/2.png)

2. use variable dynamically generate relationship to generate the hierarchy template 
3. Write another .js or go code to generate file in /date to maintain the categories relationship, then use data template to show result
### Status
- Status
    - [ ] Done but wait for optimization
- Source code location
    - Static/tree/category_tree.js 

### Usage
- If you want to add article as main-category __A__ and sub-category __B__ , add information in meta-data categories = ["__A__","__A/B__"]
- Ex: categories = ["service-design","service-design/ecosystem"]






### Survey possible solutions 

- [Solution 1 - hugo-nested-menu-example](https://github.com/vjeantet/hugo-menu-show)
  -  [Demo](http://vjeantet.github.io/hugo-menu-show/)
- [Solution 2 - hugo-tranquilpeak-them](https://github.com/kakawait/hugo-tranquilpeak-theme)
  - [Demo](https://tranquilpeak.kakawait.com/categories/)
- [Solution 3 - section tree](https://github.com/bep/hugotest)
  - [has bug in my theme](http://experiments.wemakesites.net/css3-treeview.html)

Miscellaneous

- [Github Issue Discussion 1](https://github.com/gohugoio/hugo/issues/465)
- [Github Issue Discussion 2](https://github.com/gohugoio/hugo/pull/3309)



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


recommendation for content management
- [Discussion](https://discourse.gohugo.io/t/discussion-content-organization-best-practice/6360/2)