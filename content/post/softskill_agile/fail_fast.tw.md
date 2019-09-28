+++
date = "2016-09-14 23:15:29"
categories = ["agile"]
tags = ["TGDF2016"]
title = "TGDF 2016 - Fail Fast 閃退" 
toc = true
+++

# Fail Fast─為什麼閃退是好事 (Undone)


Speaker:  雷亞 Co-founder 楊善詠

## 挑戰
- 技術人才培育
- 跨平台架構

__事實上是救火雷亞__

### 員工人數遽增
2011 , 16人
2016,  >100人

__死亡行軍：規格變更__

Reference: [SE系統工程師](http://tw.ikanman.com/comic/8128)

### 種下惡因？
效能問題？
為了方便？用最簡單方式測試

### BUG？
自己的BUG自己修？那別人的呢？
來自game engine 的問題

###  無法修正問題？
=> "改變規格"，讓玩家看不到

### 遊戲前端很難測試
## 可能的解法

避開錯誤（X）
=> 盡可能提早發現錯誤
=> fail fast


### 簡單Example
#### Defensive Programming 防禦性程式設計(避免software crash為目的）

- 接到 null 是正常的現象嗎？
- 淺在造成bug，卻可能造成無法找出問題

** NullPointerException
** Debug assert

Check input value ( use assertion too!)
Add up the diagnosis info for future


### Design by Contrast (DbC)
- Assertion 可以做到 input contract
- Output contract:檢查回傳值
- Invariant Constract: 保證物件的一致性

DbC : A kind of unit test

### Unit Test: Hard Part

1. Game Program is high human-interaction ( UI testing tool )
2. Game Program change spec. frequenecy (也很主專)
3. 學校沒有教你怎麼寫測試

### 前端
非常難測試

### 後端
直到開始後端，就開始測試
動態行別的語言，方便寫測試
Framework: Python flask

### Test 關鍵
- 與外界互動
- Input/output

__建立Mock Object，演一場假戲__

### Decoupling
- Single Responsibility (單一的功能)
- Dependency Injection
- 詳細起看 __SOLID原則__

希望目標

- 提高改變規格的彈性
- 遊戲核心邏輯和遊戲呈現要分乾淨


Code Coverage
縮短開發到回饋時間

## CI 持續整合

- Development => build on Mac => Deploy to Device => Testing
- 花時間又重複性的工作 => 自動化
- Ex: Jenkins

Commit => Automatic Build Task => deploy to Device => Testing

週期性 QA
(Image)

降低未知的風險



Reference

- [TGDF簡介](http://www.tgdf.tw/archives/member/shan-yung-yang)
- [作者原 slide](https://docs.google.com/presentation/d/1WYDpUjt5hWnE30rphzQM_Tw91kASht5lVjA-YY9IL4M/edit#slide=id.p)