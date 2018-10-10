## Hierarchy categories (main-category and sub-category)
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


