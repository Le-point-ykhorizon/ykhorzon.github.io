# My Tech Blog

# Todo List
1. Porting this [hexo-theme-beantech](https://github.com/YenYuHsuan/hexo-theme-beantech) to hugo
2. Search in website content
3. RSS

All the solutions of 2. 3. are in [offical web - Tools](https://gohugo.io/tools/). But I need to integrate them.

# Quick reminder location for Development/Maintainence

Where is javascript and Page Header
- theme/layout/partials/base/metas.html
- theme/layout/partials/base/imports.html
- theme/layout/partials/base/scripts.html

# Plugins

1.Hierarchy category (main-category and sub-category)

- Status
    - Done but wait for optimization
- Source code location
    - Static/tree/category_tree.js 

- Usage
    - If you want to add article as main-category __A__ and sub-category __B__ , add information in meta-data categories = ["__A__","__A/B__"]
    - Ex: categories = ["service-design","service-design/ecosystem"]



# Functions

1. Multi-language content management




# Implementation Details

## 1.Hierarchy category

Idea
1. use variable dynamically generate relationship to generate the hierarchy template 
2. Write another .js or go code to generate file in /date to maintain the categories relationship, then use data template to show result

- [] manage tags/catagories/keyword/series 
- [] image management
- [] drop-down nav bar for sub-directory
- [] search function (Google or inline search)

recommendation for content management
- [Discussion](https://discourse.gohugo.io/t/discussion-content-organization-best-practice/6360/2)



