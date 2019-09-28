+++
author = "ykhorizon"
date = "2018-04-28T23:43:06+08:00"
title = "硬體開發流程與計畫管理 for Startup Part I: 硬體開發流程"
categories = ["hardware"]
topics = []
keywords = []
tags = []
type = "post"
+++



## 為什麼 <span style="color:red;">軟體工程師</span> 需要知道 <span style="color:blue;">硬體開發流程</span>？

設想一下，你是一家新創公司頭號軟體工程師，公司的第一個產品是一台機器人，你完全沒摸過硬體，當你和硬體工程師要合作開發，你該怎麼辦？

- 軟體工程師對 __硬體開發流程__ 通常是一無所知，造成與硬體工程師（機構與電路）溝通產生障礙，無法理解對方的考量，造成團隊衝突。
- 開發過程中，軟硬體產品在軟體與硬體有部分相依性問題，尤其是在測試階段，軟硬硬體必須整合討論，才能完成完整測試。

> 打破這條鴻溝的辦法是：明白對方的開發流程，理解每一個軟硬體相依性的部分，以及硬體工程師的考量，知道更多硬體工程師在想什麼，建立溝通前的情境脈絡，有助於減少溝通成本，讓合作中的問題更快浮現，找出癥結點。

<!--more-->

# 硬體開發流程
<br>
主要分成幾個階段：

1. 選擇解決方案 Solution Selection
2. 概念證明 Proof of Concept
3. 驗證 Verification
4. 生產準備 Pre-production
5. 產品認證 Certification

------------
## 1.選擇解決方案 Solution Selection

Solution 通常是 MCU/MPU 晶片組或其他相關，需要考量以下幾點：

__1.1 New features for your product__

> 一般來說，Startup的產品通常是沒有前人作過，可能需要仰賴 Solution 的 New Features。舉例：AI chip (包含Deep Learning Accelerator)

__1.2 支援 Supports(Demand & Supply)__

> 選擇的 Solution 是否有足夠的文件、廠商客服或社群資源，避免遇到 bug 或 問題無從求助。 Open Source 的 Solution 通常都是 Community，支援的大小和能力通常容易觀察；相反，選用冷門的 Solution 可能會遭遇前面的提及的問題。

__1.3 時機 Timing(Mature/JIT/Not Ready)__

> 採用 Solution 考量是否足夠成熟；通常產品會帶動相關技術 solution，EX：gopro + ambarella SoC

__1.4 成本 Cost__

> Startup 需要控制好 solution 的 cost，但不需完全著重於 cost-down ，因為如何努力壓低成本，始終無法比大公司的生產成本更低；因此 Startup 更應做出自己的產品特點，『打中客戶的痛點』更為重要！


__1.5 效能 Performance__

> Solution 的 Performance 必須要能實現出產品的 Feature


__1.5 Roadmap__

> 我猜測是 Solution 發展的歷程，開源硬體相對透明公開，閉源在開發中不公開，無法確定往後方向

__Open Source Solution vs Disruptive Solution__

下圖的重點為： New Features 和 Support 的差異不同
![](/content_img/hw_development_for_startup_part1/vs.jpg)
2018/4/25, Presentation from Antony Ko ( umbo CV, Hardware VP )

------------
## 2.概念證明 Proof of Concept

打造硬體相關任務

- Schematics 布局圖
- Part sourcing 將產品部件，可以外包出去
- PCB layout
- PCB fabrication 快速打樣
    - 掏寶有廠商可以協速快速 Fab，大約一星期內就可以收到成品
- ID(Industrial design) mockup/ mechanical fitting
- functional sample

我從軟體產品開發的學習經驗，上述都是怎麼達成（How）PoC 的一個實作環節，一位優秀的硬體工程師可以快速完成並可靠的任務；但更重要是為什麼（Why）要打造此產品，
我認為是 PoC 階段的核心任務是：

- 驗證產品解決使用者痛點
- 獲取回饋，修正方向

> PoC 作為__早期偵測產品失敗的第一道防線__，必須搭配__使用者研究__（design thinking/google sprint) 等方法一起使用。
>
> 將 Prototype 實際給 User 使用過，收集使用者回饋（可能包含量化或質化），__驗證產品假設（是否有真的解決 User 的痛點）__，能才算是完成 Proof of Concept 的一次 iteration。這通常是硬體工程師缺乏觀念的部分，認為產品開發要一路殺到生產端，但實際運作不一定是如此。

------------
## 3.驗證 Verification

我的猜測，驗證 Verification 是產品功能確定後，專注於功能性的驗證，以及產品穩定性與環境測試

- Engineering test plan 
    - 先找類似產品的 test plan 來參考
- Quality Test Plan
- Facility
    - 測試包含溫度、濕度、丟來丟去、放在包裝內摔等等

------------
## 4.生產準備 Pre-production

產進進入準備生產階段，必須考量一下問題：

- Production test plan (Yield Rate)
- Logistic 
    - 零件沒有買到，所有人都在等零件
- SMT,DIP and assembly 
    - 組裝很容易出問題，最好要自己組果 20~40台
- Test/configuration & software
    - 測試用搭配的軟體，要些思考並準備好
- Fixture & facility

------------
## 5.產品認證 Certification

產品販售到各地區，各地區有都相關規範或認證需要通過，才能在當地販售，因此必須準備相關問題：

- 從 PoC 階段，就要開始找 Certification Lab 討論認證
- 自己找適合產品的認證規範
- 文件、包裝與說明說
- Lab 說的不一定對
    - Why? 因為 Lab 有可能沒遇過你的類型的產品，也不知道要怎麼測試



<br>
# 將開發工作拆解到職位 （硬體部分）

## 電機/電子工程師 EE

- Specification 撰寫產品規格書
- circuit design 電路設計
- layout 佈線
- build 把東西做出來
- test 電路測試

## 機構工程師 ME

![](/content_img/hw_development_for_startup_part1/me_development_sop.jpg)
2018/4/25, Presentation from Antony Ko ( umbo CV, Hardware VP )

- 工業設計 Prototype 3D 設計
- 工業設計 Mockup
- 拆解圖
- Mechanical Mockup & Review
- Tooling Build & Trial
- Test

模具花費時間

- 6 week 塑膠模具
- 8 week 金屬模具


# Reference
- 2018/4/25, Presentation from Antony Ko ( umbo CV, Hardware VP )
- [ID, Industrial design, wiki](https://en.wikipedia.org/wiki/Industrial_design)
- [Prototype, wiki](https://en.wikipedia.org/wiki/Prototype)
- [Mockup, wiki](https://en.wikipedia.org/wiki/Mockup)