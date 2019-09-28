+++
author = "ykhorizon"
categories = ["cs","cs/machine-learning"]
date = "2017-07-15T16:19:13+08:00"

draft = true
keywords = ["key", "words"]
tags = ["machine-learning", "coursera-note"]
title = "機器學習 Photo OCR 範例"
topics = ["topic 1"]
type = "post"

+++

OCR( [Optical character recognition](https://en.wikipedia.org/wiki/Optical_character_recognition) ) 全名為[光學字元辨別](https://zh.wikipedia.org/wiki/%E5%85%89%E5%AD%A6%E5%AD%97%E7%AC%A6%E8%AF%86%E5%88%AB)，以影像辨識技術判斷出照片中的文字。

課程影片提供簡單的 OCR 步驟為下：

1. text detection
2. char. segmentation
3. char. classification

通常這樣流程為 __machine learning pipeline__，目的是將問題拆解成子問題，個別子問題互相關連性低，可分派給不同工程實作。
每一個步驟（component, module) 對 performance 都有重要的影響。

> 如何拆解成 pipeline ，似乎是關鍵。


## Sliding Windows

在影像辨識的問題，其中 行人辨別( pedestrian detection ) 是一個經典例子，其中會利用長方形區塊( patch ) 框選出行人在圖片中的位置。
該標示的長方形區塊就是 sliding windows。

### Definition
slide window 是一切割的好長方形區塊，用來限制要被 detect 的區塊
step-size / stride 代表 sliding window 一次移動距離

# Articial Data sythesis

sythetic data

Get more data

- Artigifical data synthesis
- Collect/label it yourself
- Crowd sourcing

計算兩者個別需要多少時間？選擇效益比較好的


# Ceiling analysis
