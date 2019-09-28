+++
author = "ykhorizon"
categories = ["agile"]
date = "2017-08-02T12:41:57+08:00"
description = "DevOps這麼紅？到底在紅什麼？基本功又有哪些？"
keywords = []
tags = ["talk", "agile"]
title = "DevOps 全棧工程師-活動心得"
topics = []
type = "post"

+++

Speaker: 

- [odd-e 柴叔(柴鋒)](https://www.odd-e.com/about/feng.html)

(P.S. 本文演講消化後心得，加入部分我自己觀點)

![](/content_img/computer/devops/intro.jpg)
# 歷史脈絡
## 開發、維運，分分合合
柴叔從開發歷史的脈絡娓娓道來，從服務或應用簡單的年代，開發（Development)與維運(Operation)可以一起包辦，但隨著複雜度的提高，逐漸將開發（Development) 與維運(Operation)獨立成兩個團隊。久而久之，雙方的溝通本成增加，合作程度低下，最終造成總體效能下降(開發與測試的關聯，但這邊不詳細敘述)。人們開始思考需要一個穿針引線的角色，他/她需打通開發與維運流程，增進溝通效率，共同協作完成任務，目前當紅的 [__DevOps__](https://zh.wikipedia.org/zh-tw/DevOps)的一種解釋。

## 你以為過去沒有 DevOps? 
在遠古開發時代(?)，沒有 Docker 或 Ansible 這類工具。但別忘了其實底層絕大多數的工作，都可以用 shell script 完成，可見 shell script 這類基本功有多重要。時代在改變，但要完成的工作並沒有改變，大多是變複雜，解決問題的觀念類似。

再者，microservice 這類型的觀念，其實也早在 Unix 哲學([Unix philosophy](https://en.wikipedia.org/wiki/Unix_philosophy))中被提及，差異是在不同系統層級實作( Do One Thing and Do It Well. 可以對照到 microservice)，當代有更方便工具，抽象化細節與簡化操作流程。

__框架工具之於觀念__

> 工具只是溝通工具，而不是溝通的本身 <br>
> 舉例：Jenkins只是CI的工具，CI的關鍵是CI觀念本身，不管用任何方式達成都好

__框架工具之於基本功__

> 框架不會幫你解決產品的問題，幾乎與你的產品無關 <br>
> 基礎不紮實，只花時間在學習框架或工具，遭遇的狀況牽扯底層或基本面，也是無法處理

# 舉例：Java 工程師 v.s Ops 維運工程師

![](/content_img/computer/devops/java_vs_devops.jpg)
上圖比較 Java 工程師與 Ops 工程師的技能對照，一目了然自己缺少哪個技能。一般前段或後端工程師的 skill set 從 bottom-up 到 top-down 大家都很清楚，但提到 DevOps 大家似乎被 Top-down 工具給迷惑住了！這算是一張check list，提醒自己是否還缺少哪個部分。

## 經驗呼應

過去在學習 Linux 系統管理時，常在環境建制和系統管理上碰到卡關，當然我只會 google solution (最常見就是 google 出一堆 command line 指令照打一次，問題就解決但根本沒有理解)，現在回頭想想，當我對整體(linux系統和服務)理解有限，遇到問題當然就會卡住。

- __從眾多要學習的事情中，辨識出最重要的基礎功，投資時間在上面，避免見樹不建林__

# 參考
- [Unix philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)
- [Devops 其實只是原力](https://medium.com/@ypochien/devops-odd-e-c51901483724)