+++
author = "ykhorizon"
date = "2018-08-03T23:37:51+08:00"
title = "Personal Kanban 實踐後的第一次檢討"
categories = ["workflow","workflow/personal-kanban"]
topics = []
keywords = []
tags = ["workflow","personal-kanban"]
type = "post"
+++

# 文章要點

> - Personal Kanban 使你專注於少數的焦點（重要的事務），並提供一種視覺化的機制，易於凸顯出執行效率上的問題，便於改善與優化
> - 但實際在個人工作使用中，會遭遇什麼問題？在本文章中會告訴大家遭遇的問題，嘗試提出應對方案

<!--more-->

# 現況

我所採用是個人看板（Personal Kanban）搭配 [番茄時鐘法](https://flipedu.parenting.com.tw/article/3881) 的方式，管理我的工作與生活事務。
主要建立四個 List 在我的工作流程中，要作的事情我稱為『Task』或『Task Card』上面寫要作的事情的內容；當 Task 處於不同的List中，代表所處的狀態不同，狀態如下：

- todo ：要做的 Task
- doing ：目前正在做的 Task
- done ：完成
- review：回顧任務結果
 

__主要四種 List__
<img style="width:640px;"src="/content_img/personal_workflow/fig1.png" >

並將各種不同來源的task劃分為許許多多的 todos list，如下圖

__Todos 分成很多種類__
<img style="width:640px;"src="/content_img/personal_workflow/fig2.png" >

## 運作流程

### 執行 Task

當在執行某任務時，將該 task 從 Todo 移到 Doing ，處於 Doing 的 Task 用 TMetric 紀錄花費時間，方便一天結束後觀察工作情況；另外，使用番茄時鐘創造工作節奏，25分鐘為一段專注時間，5分鐘休息，此後重複循環，直到任務完成，或者是集中力下降，就得離開座位進行長時間休息。

__番茄時鐘創造工作節奏與Tmetric紀錄花費時間__
<img style="width:640px;"src="/content_img/personal_workflow/fig3.png" >

### 結算

目前採用__每一天結算一次__，檢討一天的工作花費時間

TMetric 網頁中可以查看當天 trello 中個別 task 的花費時間，如下圖
<img style="width:640px;"src="/content_img/personal_workflow/fig4.png" >

將時間消耗紀錄於 OneNote 方便回顧，如下圖
<img style="width:640px;"src="/content_img/personal_workflow/fig5.png" >

## 問題浮現
> 我的工作流程，在實際運作過約 2個月之後，一些問題逐漸浮現，我在『實踐經驗反省』的段落會詳細說明。





# 實踐經驗反省

以下我將分成幾個部分討論

## 良好的部分

- 初步視覺化我自己的任務
- 以番茄中調整工作節奏

## 不好的部分

- 對於 kanban 的精神有點模糊，不夠了解
    - 沒有限制明確的 WIP 數量

## 重新學習 Personal Kanban 精神

在實際操作之後，我發現我對 Kanban 的核心概念不夠透徹，因此我閱讀了 [Ruddy Lee] (https://ruddyblog.wordpress.com/) 前輩的 Blog 相關文章 [[2]](https://ruddyblog.wordpress.com/2014/09/21/%e9%81%8b%e7%94%a8%e5%80%8b%e4%ba%ba%e7%9c%8b%e6%9d%bf%e5%81%9a%e6%99%82%e9%96%93%e7%ae%a1%e7%90%86/),[[3]](https://ruddyblog.wordpress.com/2014/08/25/%e7%94%a8%e4%be%86%e6%8f%90%e5%8d%87%e5%80%8b%e4%ba%ba%e6%95%88%e8%83%bd%e7%9a%84%e3%80%8c%e5%80%8b%e4%ba%ba%e7%9c%8b%e6%9d%bf%e7%b3%bb%e7%b5%b1%e3%80%8d-personal-kanban/),[[4]](https://ruddyblog.wordpress.com/2018/01/11/%E5%AF%A6%E8%B8%90%E4%B8%80%E6%97%A5sprint%E7%9A%84%E5%80%8B%E4%BA%BA%E7%9C%8B%E6%9D%BF/),[[5]](https://ruddyblog.wordpress.com/2018/01/08/%E4%B8%80%E5%80%8B%E4%BA%BA%E5%A6%82%E4%BD%95%E6%96%BD%E8%A1%8C%E6%95%8F%E6%8D%B7/)，文章很詳細非常值得一讀，我自行統整出幾個要點如下：


__Personal Kanban 的核心概念：__

- __視覺化__：把你手頭的工作流程畫出來
- __限制 WIP__ (Work in Progress, 也就進行中的工作，同時也是尚未完成的半成品) 
    - 根據軟體開發/工業生產的理論基礎，調整與限制 WIP 可以找出最單位時間產出量（Through Put)
- __管理流程化__：透過反省、分析，試圖最佳化你的工作流程與方法


__彙整後調整架構：__

- Task card: 紀錄你要執行的任務，可以在 kanban 改變的 List 位置，代表任務的目前處於的狀態
- List
    - Todos List: 寫下你要行的任務
    - Ready List: 規劃並以優先順序安排你今天要執行的任務
    - Doing List: 目前正在執行的任務，限制 WIP 應用於此 LIST 正在執行中 task 的數量 < 2～4 項
    - Done List: 已經完成
    - Review List: 檢討任務執行的好與壞

完成後的 trello personal kanban 如下圖：
<img style="width:640px;"src="/content_img/personal_workflow/fig6.png" >

__全景模式與專注模式的切換__

- 類似於番茄中定義的 25分鐘 / 5分鐘，分配工作節奏，25分鐘專注於單一任務上，5分鐘休息（順便可以讓眼睛休息），但同時回到整體的kanban，思考是否有自己目前正在執行的項目與整體大目標的關係。

__事先規劃__

限制 Ready 數量 / 事先安排(最好是前一天)在 Ready 中的 Task ，並安排優先順序。
最後一天結束後一定要 review 一下完成的進度，並告訴自己還有哪些任務上未完成，明天繼續。

## 自省的改善建議

### 1. 太多 List 、太多根本沒有開始的 Task

刪減多餘 List 與脫太久沒作的 Task：

>   
>   - 有些項目長期，不適合直接放在 kanban 中(e.g. 運動、記帳)，理當搭配 google calendar 設定為每週固定時間執行
>   - 減少寫 Task，更嚴謹的思考，到底有沒有必要作這件事情
>   - 有些放置太久的任務，未來也沒有執行的必要的話，可以直接刪除

Task 並未標記 Label（沒分類工作類別)

> - Task 種類應該用 Label 分類，而非建立不同的 List 存放，強迫自己思考自己在哪一類的事情
> - 用 label 分類 task，在統整 done list 中的任務時，可以便於分析自己的工作是否專挑某一種工作，又或者哪一類公做作比較慢 

如何知道 task 寫的內容是否恰當？

> - 至少具必 __明確性__、__可執行性__、__可驗收性__
> - 寫不好也沒關係，反正可以在修正呀！寫下去就對了！

任務的大小如何決定？（舉例：完成某某線上課程，耗時3個月)
  
> - 目前無好方法，但確定的是『當任務太大』和『Task 卡很久』時，就一定要設法拆解 Task
> - 拆解成小任務，如果重要規劃固定時間執行，並分批進入 personal kanban 完成

### 2. 執行的問題

歪樓問題：正在執行 task 和 目標不一致
  
> - 檢查每一天完成的 task 和我的大目標是否有一致？
> - 每個 task 在 番茄時鐘運行的過程中是否有專注？品質是否足夠？只有自己捫心自問才知道

心態因尚未規劃工作的怠惰，因此沒有執行kanban

> - 前一天事先睡前規劃好隔天明確的 Task，放入 Ready List 中，明天一早起床不需思考，直接開始消化 Ready List

### 3. 檢討的問題

如何 Review 更有效？
   
> - 目前的方法中，每天檢討專注在時間花費在哪些任務，而非達成了哪些任務
> - 因此改成一天結束 check personal kanban 和 tmetric 時間花費，同時卻檢查完成任務和花費時間
> - 到底有沒有認真檢討？還是自欺欺人而已？

Task Card 執行經驗與結果無法累積
    
> - Task card 內容可以詳細，方便執行，但結束後結論和過程要 archive 進入 OneNote 筆記，累積成知識系統，方便傳承和重新使用；盡量保持 personal kanban 為單純觀察工作流程的工具，被免過度複雜化的使用


### 4. 全域視覺化問題

多個 Project 同時運行搭配多個看板，造成無法有完整全景視角

> - 使用 trello 中的 copy task card 功能，將 task 匯集到單一地方（personal kanban）


# 修正後的混合方法

內心的OS

> 我認為只有 Personal Kanban 不足以滿足長期規劃的任務，因此我演化出自己的混合解法


## 概念

我的觀察是：personal kanban 關注於顯現出 task 的__狀態的呈現__，便於找出系統性問題；同時，流程被強迫轉換成有順序（kanban 由左而右)的 list，如果沒有刻意作紀錄的話，相對是__中短期的視角__；

傳統以月曆為時間規劃方法，著重於期限與時間區段的任務，__視角更為長期__。因此我依照『與成功有約』中的『以終為始』的概念，先在月曆中制定目標期限，再拆解成月和週小目標，再將可以達成目標的大任務拆解成小並且能夠實行的 task card 進入 personal kanban 執行與規劃。


『與成功有約』中有將任務劃分為四種類型，由對你人生的影響程度排序（依據長遠角度）依序為：

1. 重要 / 不緊急
2. 重要 / 緊急
3. 不重要 / 緊急
4. 不重要 / 不緊急

作者史蒂芬·柯維認為人們應該專注於 __重要 / 不緊急__ 的任務，這類的任務往往和長期目標與基礎功夫的扎根很有大的關係；當一個人疲於奔命，忙著應付 __重要 / 緊急__ 和 __不重要 / 緊急__ 的任務時，會遲遲無法往更遠大的目標前進；當一個人總是在 __不重要 / 不緊急__，其實就是逃避、偷懶或處於身不由己的位置。



## 事先規劃 "重要 / 不緊急" 的任務

依據此原則，我將 __重要 / 不緊急__ 的任務，__使用 Google 月曆__ 規劃在每週固定的時段，時間可以稍微有彈性，但任務內容執行__內容必須極度明確__，例如：

- 運動星期一18:00~19:00 慢跑 4k 包含暖身與收操(如果加班就移到 22:00~23:00)
- 英文口說練習挑選一篇 National Public Radio的新聞，用影子法訓練口說。
  
這類型 __重要 / 不緊急__ 的任務不需進入 kanban 的流程，但偶爾會有例外。有辦法固定時間，就設法用 Google Calendar 規劃，搭配自己建立的 check list（我是使用 Google Doc sheet），了解這些任務長期執行達成狀況。

Google 月曆事先規劃，如下圖
<img style="width:640px;"src="/content_img/personal_workflow/fig7.png" >

Google doc sheet 紀錄執行住況，如下圖
<img style="width:640px;"src="/content_img/personal_workflow/fig8.png" >


## 動態處理 "其他類型任務"

其他三種類型的工作，則盡量進入 personal kanban 流程進行管理

搭配工具

- Personal Kanban 使用 trello，搭配 TMetric 對 task 計時 
- Tomato Timer 調整工作節奏

# 結論

我試圖提出自己的混合作法，設法讓自己工作流程可以更順暢，期待一個月後 2018/9/5 的第二次 review

# Reference

- [1] [Ruddy Lee 分享空間](https://ruddyblog.wordpress.com/)
- [2] [運用個人看板做時間管理, Ruddy Lee](https://ruddyblog.wordpress.com/2014/09/21/%e9%81%8b%e7%94%a8%e5%80%8b%e4%ba%ba%e7%9c%8b%e6%9d%bf%e5%81%9a%e6%99%82%e9%96%93%e7%ae%a1%e7%90%86/)
- [3] [用來提升個人效能的「個人看板系統」– Personal Kanban, Ruddy Lee ](https://ruddyblog.wordpress.com/2014/08/25/%e7%94%a8%e4%be%86%e6%8f%90%e5%8d%87%e5%80%8b%e4%ba%ba%e6%95%88%e8%83%bd%e7%9a%84%e3%80%8c%e5%80%8b%e4%ba%ba%e7%9c%8b%e6%9d%bf%e7%b3%bb%e7%b5%b1%e3%80%8d-personal-kanban/)
- [4] [實踐一日Sprint的個人看板, Ruddy Lee ](https://ruddyblog.wordpress.com/2018/01/11/%E5%AF%A6%E8%B8%90%E4%B8%80%E6%97%A5sprint%E7%9A%84%E5%80%8B%E4%BA%BA%E7%9C%8B%E6%9D%BF/)
- [5] [一個人如何施行敏捷, Ruddy Lee ](https://ruddyblog.wordpress.com/2018/01/08/%E4%B8%80%E5%80%8B%E4%BA%BA%E5%A6%82%E4%BD%95%E6%96%BD%E8%A1%8C%E6%95%8F%E6%8D%B7/)