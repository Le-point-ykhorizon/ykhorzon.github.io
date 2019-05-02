+++
categories = ["blog", "blog/hexo"]
date = "2017-01-24 21:58:01"
tags = ["Hexo", "Blog"]
title = "實用hexo-抵達新手村"
draft = true
+++

## 從這篇文章得到

- Markdown 初次品嚐
- 如何搭建起一個Hexo(有一點氾濫的主題)
- Hexo基礎操作(同上)


# 目錄
<!-- toc -->
<!-- more -->


# Markdown (undone)


我自己選用markdown的主要原有：

- 可閱讀之原始檔，是一種容易移植、通用的格式
- 恰到好處的結構化語法，我可以接受

可以看看 Github 官方的 markdown 教學文件( Github上不少人也用markdown .md作為程式碼文件之格式)

- [Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
- [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

如果懶得看文件，直接玩玩看線上的 markdown editor，親身感受一下markdown的風格。

- [markdown-here](http://markdown-here.com/livedemo.html)
- [stackedit](https://stackedit.io/editor#)

# Hexo 簡介 (undone)

hexo 是一款 static page generator for blog，基於 node.js


# 基礎使用問題 (undone)


## 基礎指令 (undone)
[Commands](https://hexo.io/docs/commands.html)

## Tag plugin (undone)
當 markdown 內建的語法不能滿足你時，可以考慮看看在 [Tag plugin](https://hexo.io/docs/tag-plugins.html)
能否找到你所需。例如：引用(Block Quote)、程式碼區塊(Code Block)





## Theme 挑選

我的考量：簡單、快速生成為首要考量，美化可以自己土炮

- 選擇theme除了好看之外必須考慮blog文章增加後，generate的時間

(教你定制Hexo的landscape打造自己的主题)[http://www.jianshu.com/p/b96fd206571a]



- 怎麼客製化 Theme

(hexo official)[https://hexo.io/docs/asset-folders.html]
## 文章管理 - hexo-cli (undone)

### Template (undone)

## 加入圖片 

### 路徑
hexo 中 image 是一種 asset，主要可分成理種

- post asset
- global asset

先修改blog的_config.yml 中 post_asset_folder 從 false改成 true。
當你 hexo new post  之後
{% asset_img rst.png %}


### markdown方式
Code (external/internal):
{% codeblock lang:markdown %}
![test](https://github.com/favicon.ico)
{% endcodeblock %}

但你會發現每次要打path，前半部都一樣很煩，可以開啟

### asset_img

### 可控制圖片小 Raw Html
Code (internal/external for sizing):
{% codeblock lang:html %}
<img src="https://github.com/favicon.ico" width="48">
{% endcodeblock %}

[Resize Image in Markdown](http://stackoverflow.com/questions/24383700/resize-image-in-the-wiki-of-github-using-markdown)
## 站內連結 (undone)
## Tag 與 Category管理 (undone)


# Reference

- [Hexo-Workshop](https://github.com/techlahoma/Hexo-Workshop)
- [Hexo使用攻略](http://ijiaober.github.io/2014/08/05/hexo/hexo-04/)
