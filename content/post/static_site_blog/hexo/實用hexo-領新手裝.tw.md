+++
categories = ["blog", "blog/hexo"]
date = "2017-01-24 16:15:39"
tags = ["Blog", "Hexo-Advanced"]
title = "實用hexo-領新手裝"
draft = true
+++

> 當你把hexo當作Content Providing的武器
> 長時間使用並認真感受，才能考驗她的架構與設計

## 從這篇文章得到

- 將Hexo作為Content Providing 的工具，你將會真實面臨使用情境，開始尋找應解決工具

## 目錄
<!-- toc -->
<!-- more -->


# 我的撰寫流程 - User Story

(0) 挑選出適合的主題，撰寫成為文章。我挑選題目大致上分成三類

- 活動、社群聚會的心得內容
- 自己規劃想要學習的系列文章
- 書本、課本筆記反芻

(1) 安裝好[Browsersync](http://chenyuhsin.github.io/f2e/2016-0720-%E5%9C%A8-hexo-s-%E9%A0%81%E9%9D%A2%E8%87%AA%E5%8B%95%E5%88%B7%E6%96%B0.html)後，開啟iterm，分別執行

{% codeblock %}
    hexo g -w # Generate by watching change files
    hexo s    # Serve public articles(non-draft) on local
{% endcodeblock %}

(2) 開啟 Atom，開始編輯內容
(3) 打開 Chrome 無痕視窗並[關閉Cache功能](http://stackoverflow.com/questions/5690269/disabling-chrome-cache-for-website-development)，Preview顯示效果

步驟2. 3.瘋狂循環，直到文章定稿

(4) Deploy文章到github page上

{% codeblock %}
  hexo d -g # Deploy post articles to github page service
{% endcodeblock %}

(5) 分享文章於社群或自我推銷，藉由信箱或Disqus __取得回饋__ 後修改文章


# 本質 - 理解hexo source code (undone)

- 對javascript有基本認識，不會害怕trace code(!?)
- 可以打自己的plugin或script加速流程


# 升級hexo裝備
## 受眾互動
### 留言功能

- https://blog.ivanwei.co/2016/01/03/2016-01-03-add-disqus-to-blog-by-hexo/
- http://morris821028.github.io/2014/04/12/web/hexo-comment/

## Google Analytics
[Jonathan Klughertz, Add Google Analytics](http://www.codeblocq.com/2015/12/Add-Google-Analytics-to-your-hexo-blog/)

## SEO 搜尋引擎最佳化 (undone)

## 撰寫流程優化


### 即時載入更新頁面

當你一修改文章的內容後，Browser會自動重新整理。熟悉網頁開的人，會稱此功能為 __liveReload__。可參考一下文章，建立此功能。個人目前推薦 [Browsersync](https://browsersync.io/#install)，它還有很多許多強大功能可以玩耍，自行服用。

- [Hexo 页面自动刷新与移动端调试](http://moxfive.xyz/2016/03/27/hexo-browsersync/)
- [在 hexo s 下實現頁面自動刷新，Browsersync套件](http://chenyuhsin.github.io/f2e/2016-0720-%E5%9C%A8-hexo-s-%E9%A0%81%E9%9D%A2%E8%87%AA%E5%8B%95%E5%88%B7%E6%96%B0.html)

方法比較

- [Hexo不重新生成也可预览](http://jerry011235.github.io/2015/05/07/Hexo%E4%B8%8D%E9%87%8D%E6%96%B0%E7%94%9F%E6%88%90%E4%B9%9F%E5%8F%AF%E9%A2%84%E8%A7%88/)

Caution: 我使用 [hexo-browsersync](https://github.com/hexojs/hexo-browsersync) plugin 發生 render sidebar跑出亂碼的狀況。
因此我改用，改用原生的[Browsersync](https://browsersync.io)，在你的hexo資料夾下，輸入以下指令：

{% codeblock %}
browser-sync start --server 'public' --files 'public'
{% endcodeblock %}

Results: 我猜測是hexo-browsersync地方寫壞了，我看github有2年沒更新。等我開始trace hexo source code在來看要不要幫忙fix bug。

### 管理多重blog文章 (undone)



## Design & Layout

### 改變 theme markdown style

只要你具備css,html的基礎，自己可以trace theme中css和layout部分修改，打自己可blog的外觀

Exampel : CSS 最上方 nav-bar 的字體顏色修改

修改 themes/landscape/source/css/_partial/header.stylus 中 __$nav-link__ 的部分

{% codeblock lang:css %}

$nav-link
  float: left
  color: #000
  opacity: 0.6
  text-decoration: none
  text-shadow: 0 1px rgba(0, 0, 0, 0.2)
  transition: opacity 0.2s
  display: block
  padding: 20px 15px
  &:hover
    opacity: 1
    
{% endcodeblock %}

### 以 landscape theme 為例的教學
[教你定制Hexo的landscape打造自己的主题](http://www.jianshu.com/p/b96fd206571a)

### 目錄或摘要

- Content of Table
  - https://github.com/bubkoo/hexo-toc
- multi-level categories 包含 counting
- Post 文章收納
  - `<!--more--> `
  - [auto_excerpt](https://github.com/iissnan/hexo-theme-next/issues/62)

- 文章摘要 auto_excerpt

### 英文字體美化

[google font](https://fonts.google.com/?category=Handwriting)

在 themes/landscape/layout/_partial/header.ejs 之中，<head></head>部分，插入

{% codeblock lang:html %}
  <link href="https://fonts.googleapis.com/css?family=你的字體" rel="stylesheet">
{% endcodeblock %}

## 數學方程式美化 - MathJax (undone)

## 影片

影片
- Youtube Embedded
  - [圖片解法](http://stackoverflow.com/questions/2068344/how-do-i-get-a-youtube-video-thumbnail-from-the-youtube-api)

## 多語系支援 (undone)


# Reference

- [教你定制Hexo的landscape打造自己的主题](http://www.jianshu.com/p/b96fd206571a)
- [关于 Hexo 的若干问题](http://bubkoo.com/2013/12/16/hexo-issure/)
- [multi-level categories](http://yuchen-lea.github.io/2016-01-23-display-hexo-category-in-hierarchy/)
- [Hexo ToC](https://github.com/bubkoo/hexo-toc)

Advanced Playground
- [hexo admin](https://github.com/jaredly/hexo-admin)
