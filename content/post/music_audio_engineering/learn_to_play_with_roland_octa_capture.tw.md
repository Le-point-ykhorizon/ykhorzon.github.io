+++
author = "ykhorizon"
date = "2018-12-06T16:54:20+08:00"
title = "Roland Octa Capture interface 在 MacOS 環境設定"
categories = ["audio-engineering"]
tags = ["music-equipment"]
type = "post"
+++


## 關於常見的線材

3.5mm TRS(一般耳機孔), 6.3mm TRS, XLR(Cannon頭)

References

- [深入XLR，單聲道? 雙聲道?](https://www.jacksonlin.net/20170516-xlr-mono-or-stereo/)
- [[音響研究室] 音響插頭一點也不複雜！記住這五種插頭，你的音響之路就又進一大步啦！](https://www.cool3c.com/article/87281)
- [常見的音訊接頭，有何講究?](https://www.jacksonlin.net/20170512-xlr-trs-jack-48v/)


## 關於 Octa-Capture

這台的特色：

- input 1~2 可以設定 high-impedance(Hi-z) ，針對電吉他 direct line-in
- input 1~8 都有幻象電源 48v Phantom power
- 有 auto-sensing 的功能

<!--more-->

## 測試 Octa-Capture UA-1010

### 準備

1. 安裝 Roland 官方對應版本作業系統的 driver [link](https://www.roland.com/global/support/by_product/octa-capture/updates_drivers/)
2. 在 MacOS 10.13 中，系統預設會阻擋 interface 和 MacOS 連接，造成一直從 OCTA-CAPTURE Control Panel 找不到 Device (System Preference / Sound 也無法在 input,output看到 )；

__必須得去 System Preference > Securiy & Privacy > [Tab] General  > 點選畫面下方allow roland octa .... ，才能在系統中抓到device__ ，可參考官方 [trouble shooting](https://www.roland.com/global/support/support_news/1804131013/)

### 1. 作業系統偵測 interface (interface driver系統安裝確認)

器材接法

- Computer Playing Video or Music -(Computer audio card setting)-> Interface -> Monitor Headphone
    - 安裝是否有備系統偵測到，在 MacOS > System preference > Sound 可以看到
    - 如果有遇到沒抓到 interface，可以嘗試重新安裝 driver


### 2. DAW software 偵測 interface 和 mapping 設定

確定 interface input 和 DAW track 的對映關係
- Track live (需要在 perference 中選擇 Interface 為 OCTA-CAPTURE）
- GarageBand（自動偵測）


### 3. DAW Software 和 interface 操作

通常這個階段，需要設定 input 和 track 的 mapping，可以從 track mixer 觀察是否有吃到 input (樂器) 的訊號。

器材接法：

- Instrument - (input) -> Interface -> DAW -> Monitor Headphone


#### 3.1 監聽

- Condenser MIC - (input3, phantom power) -> Interface -> DAW -> Monitor Headphone
- Eletric Guitar -> (input1, Hi-z ) -> Interface -> DAW -> Monitor Headphone


#### 3.2 錄音

- Directly line-in audio -> Interface -> DAW(Recording)
- Eletric Guitar -> (input1, Hi-z ) -> Interface -> DAW(Recording)
