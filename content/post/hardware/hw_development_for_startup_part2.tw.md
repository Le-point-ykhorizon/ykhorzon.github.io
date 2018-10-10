+++
author = "ykhorizon"
date = "2018-05-04T19:08:57+08:00"
title = "硬體開發流程與計畫管理 for Startup Part II: 硬體開發流程中的陷阱"
categories = ["hardware"]
topics = []
keywords = []
tags = []
type = "post"
+++


# Startup 硬體開發遭遇什麼陷阱？
<br>

![](/content_img/hw_development_for_startup_part2/trap.jpg)
https://www.pexels.com/photo/close-up-finger-hurt-pain-433625/

想像一下，你是一名新創公司的頭號工程師，公司沒有資源（缺錢、缺人），又正在開發沒人做過的產品，沒有所謂的類似產品可以參考，
一切從零開始打造。新創公司與成熟公司最大差異，新創公司沒有前人累積的軟硬體、經驗與工具，可以借助節省開發，減少走冤枉路的時間，
也就是 __Not much to leverage__

>
> - what is [leverage](http://mrjamie.cc/2013/06/03/good-strategy-leverage/)? 
>
> ``from Mr. Jamie, 創業 CEO：好策略用「支點」撐起地球``

更糟的是，你的產品牽扯到硬體生產，硬體不像是軟體，只需要電腦開發與運行程式的裝置就可以；硬體製造牽扯到各種物理限制與考量，不是東西可以動就好；硬體產品不可能完全倚靠自己的公司生產，為了降低生產成本，勢必需要尋找配合的製造廠商，這又是另一個大陷阱。此外，當你的產品需要賣到不同國家，又牽扯各國的認證等等。

> 所以在硬體製造上，有哪些陷阱可以事先避免呢？

<!--more-->

# Startup 的先天限制

新創公司普遍有以下的困境：

- 有限資源 Limited Resource（沒錢、沒人脈、沒經驗）
- 需求規格的變動 Specification Change 
- __Supply chain 需要磨合的成本__：
    - 必須先知道知道 __vender 的特性__，才能確保進入 production 能順利進行

----------
## 選擇 Supply Chain Vender 時你得注意的事：

假設你的產品經過 PoC(Proof of Concept)，想要尋找完整的 Supply chain ，請 vender 協助製造生產，你可能會遭遇以下幾種 vender：

__樂觀積極 vs 嚴謹保守__

- 過於積極樂觀的 vender 對於時間預估和成本會產生很大的變數，跟你說這個產品只要__短短幾個星期__，就可以做完成；但等到約定的時間跟你兩手一攤，說：『還沒做完耶』，你對他沒輒！
- 團隊內要有老手，能夠知道 vender 提出的 schedule 是否合理，然後必須預留時間 margin，就算真的 delay 也不至於讓產品開天窗。

__能力上限__

- 有些 vender 會誇大自己的製造能力：『這個東西簡單，一定做得出來』，但等到真的開始做，才跟你說：『抱歉，做不出來』
- 要有能力知道 vender 的能力範圍，被 vender 虎爛

__做事品質的要求__

- 觀察 vender 做事情的品質、細心程度，這關係到產品成與敗
- 品牌廠最終還是要__設計測試卡關進行驗收__

----------
## 陷阱一：選擇 ODM 花費更多人力與時間

- 發 [RFQ](http://eeepage.info/name-prod/)（報價單）
- 廠商評估
- 回報價/schedule/compliance
- Review & 討論 -> 詳細規格
- RFQ2, RFQ3....

常見延宕原因：

- Quotation 尋價內容與跟催
- 技術限制（vender 就是做不出來）
- 規格的變動
- 法律文件（來回就要好幾個星期）
- 產品多個部分由多個 vendor 廠商的 coordinate
    - 經驗法則：至少要 6~10 vendor 數量才夠

----------
## 陷阱二：每個 Task 都比你預期還要久

- 你的案子對 vender 來說，priority 很低，因此都被排在很後面
- 新創公司人力有限
    -  沒有大公司的系統與體系（QA team, 採購 ... etc )，在某些工作上效率較差
- 採用 Solution 的陷阱：
    - 使用 open source 的風險：open source 改版

----------
## 陷阱三：你會忽略的 DFx (Design for X)

你的產品設計不只需要能正常運作、滿足客戶的需求，還考量很多生產、運送、安全...等考量，這類事先設計的概念成為『Design for X』，
X 可能為許多不面向，自行替換。

__Design for__

- Feature, Performance, Quality & Cost
- Purchasing : Lead-time, availability, MOQ(最小採購批量)：IC,塑膠,螺絲 (零件是否好採購)
- Safety 
    - EX:塑膠的耐燃性需求
- Manufacturing
	
	- tooling拔模角/入料點
	- 噴漆/印刷治具
    - 可組裝性
    - PCB測點 (Testing)
    - SMT vs DIP (良率會因為DIP在大量生產時造成問題，盡量選擇SMT)
    - Production test plan & FW/SW

- Logistic : 序號, 包裝運送, RMA (保固期、退貨需要知道生產日期)

----------
## 陷阱四：品管經驗不足

大家都不熟悉 Certification ，沒作過的產品不知道相關 Certification，大概有幾種，但主要還是要自己做功課

- EMI/EMC/ESD/safety

__認證需要注意：__

- 產品類別
- 地區性

__關於品質__

- 你需要 QA test plan 
    - 特別是 hardware 需要搭配 web/mobile client application, server 都要有
- 你需要建立 bug tracking system
- 購買必要的 facility （chamber之類的，測試產品在溫度、濕度等等狀態下能夠正常工作）
- 沒有時間測試每個 design change 
- VQA/IQC 允收標準 vs Yield Rate


產品賣出不等於結束

- Specification 中不穩定的 Feature 一定要持續追蹤
- Critical Issue 要花時間要了解細節
- RMA rate 退貨率的計算


# 其他
講者在演講尾端有分享一些 bonus 的 talk
<br>


----------
## 定價策略  Magic Method

__Benchmark__

- 參考類似產品的價格來定價

> 沒有類似產品怎麼辦？

__Cost + Profit Margin__

- BoM cost x2 x2

矛盾之處：

- 太貴怕賣不出去
- 能多賺點一點錢，難道就不能定更高的價錢嗎？

----------
## 定價策略的上上策 - 找個專業的 Sales

好的 Sales 可能的策略

- B2B, 價格不透明
- 綁不同的packages可以有不同的報價與付款方式（拆解 function 變成不同方案）
- 付費方式要依據不同地區的有所差異
- 不同客群能接受的價格不同(大型機構與小公司)


----------
## Planning (Magic Number)

當不知道如何規劃時，將預期的__時間與人力 X 2__作為評估數字，估算公司到那個時候是否能撐的下去，來決定是否要進行專案下去。

----------
## 產品力

這部份是我自己補充講者的內容，我解釋成『讓你的產品真正的解決使用者的痛點』，必須仰賴 User Research 和市場分析，作產品不是工程師自己關在家裡觀落陰，使用者不會憑空出現，需求也不是用想像得來的。因此，我忍為團隊必須要有專業的使用者研究員，確定產品的方向，一旦有誤及早修正。

----------
## 感想

__對於小家公司的意義__

對於小型 supply chain vendor ，以往很多 Case 都是有數量少、市場不確定高、需要跨領域整合（機構、電路、外殼、包裝...等等）的產品
除小量的生產外，還需要協助產品的優化，是一個吃力不討好的工作。

__團隊必備技能__

一個功能健全的團隊，成員必須要具備以下能力（可以一人有多種技能，但不要操死人）

- 需要一個好的 sale
- Designer 
- User Research
- 財務 管理財務
- 找錢(funding)
- 機械工程師（ME）機構設計
- EE
- Software

__Sales 很重要__

好的 sales 可以從跑市場的時間中，同時收集使用者痛點與市場現況，非常重要！



# Reference
- 2018/4/25, Presentation from Antony Ko ( umbo CV, Hardware VP )
- [leverage槓桿, Mr. Jamie](http://mrjamie.cc/2013/06/03/good-strategy-leverage/)
- [RFQ,專案產品開發時程之專有名詞 (RFQ,Kick-off,EVT,DVT,PVT,MP)](http://eeepage.info/name-prod/)