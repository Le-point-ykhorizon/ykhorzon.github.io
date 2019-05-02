+++
author = "ykhorizon"
categories = ["blog","blog/general"]
date = "2017-08-16T22:29:08+08:00"
keywords = []
tags = ["google-analytics"]
title = "Google analytics 設定快速檢查"
topics = []
type = "post"

+++

# 設定文件

- [Set up Analytics tracking](https://support.google.com/analytics/answer/1008080?hl=en)
    - 手把手教，一步一步照作基本就好了
- [Check your web-tracking-code setup](https://support.google.com/analytics/answer/1008083)
    - Trouble shooting 的部分，快速確定 Google analytics 是否正常運作
- [Adding analytics.js to Your Site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
    - 詳細解說 analytics.js 運作

# 被 ADblock Plus 雷了
在設定 Google analytics 時，一直失敗無法從 report > real-time 看到目前的狀況，顯然是出了什麼差錯。
後來從 Chrome > developer tools > network 發現https://www.google-analytics.com/analytics.js 
根本沒被載入，想說直接將網址輸入 Chrome Url bar ，才發現是 Chrome 的 plugin ADblock Plus 檔掉，關掉後就恢復正常。

> 不夠熟悉 browser 開發環境的 debugging ，類似 java developer 不熟 eclipse 會無法快速找到問題