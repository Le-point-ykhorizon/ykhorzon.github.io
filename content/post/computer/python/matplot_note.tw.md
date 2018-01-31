+++
author = "ykhorizon"
date = "2017-10-25T12:27:23+08:00"
title = "Matplotlib 基本介紹"
categories = ["programming","programming/python"]
topics = []
keywords = []
tags = ["python","matplotlib","drawing"]
type = "post"
+++


# Outline
<!-- TOC -->

- [Outline](#outline)
- [Introduction](#introduction)
    - [Figure](#figure)
    - [Axes](#axes)
    - [Axis](#axis)
    - [Artist](#artist)
- [Matplotlib, pyplot 和 pylab 傻傻分不清楚](#matplotlib-pyplot-和-pylab-傻傻分不清楚)
- [關於使用 pyplot 的 code style](#關於使用-pyplot-的-code-style)
- [Backend 是什麼？](#backend-是什麼)
- [Reference](#reference)

<!-- /TOC -->
<!--more-->

# Introduction

以下圖片為 pyplot 的重要元件，其中最重要的為 __Figure__ 、 __Axes__ 、 __Axis__ 與 __Artist__

![Screen Shot 2017-10-24 at 3](https://matplotlib.org/_images/anatomy.png)

## Figure
Figure 包含 Axes 和 canvas。Axes 為會被畫出來的角色，如 Title 、Figure legends ... etc

```
fig = plt.figure()  # an empty figure with no axes
fig.suptitle('No axes on this figure')  # Add a title so we know which it is

fig, ax_lst = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
```
可以畫出一下的圖片
![pure figure](https://matplotlib.org/_images/sphx_glr_usage_002.png)
## Axes
Axes 是 figure 上面一個區塊的呈現資料的地方，就是你畫出來的"東西"。其中每個 Axes 會包含至少2個以上的
Axis，並且可以設置資料呈現的limits, set_xlim(), set_ylim()，此外圖片標題 title 與 x-label、y-label也是他負責。

## Axis
數字座標軸，產生座標上面的 ticks，也能決定 tick 的位置與格式(Locator 與 Formatter)

## Artist
我猜測是一種 Base Class，文件說 Figure, Axes 與 Axis object 都是一種 Article

# Matplotlib, pyplot 和 pylab 傻傻分不清楚

- Matplotlib 是完整的 python package
- pyplot 是 Matplotlib 其中一個 module
- pylab 是與 matplot 並無直接關係，單純是 python 整合科學運算的平台，其中包含許多常用的 package ，EX: Numpy, Scipy , 

pylab 是什麼？可以參考一下討論：

- [用python的前辈们，pylab是matplotlib的一个模块吗，跟pyplot又是什么关系呢？](http://www.guokr.com/question/457826/)

這邊另一點要提醒，pyplot 包含一個 state-machine interface，白話文就是你不需要每次都實體化一個物件，
自動並隱含(explictly)會生成figure和axes，就能享受 Object-oriented plotting library，如同下面這段程式碼：

``` lang=python
x = np.linspace(0, 2, 100)

plt.plot(x, x, label='linear')
plt.plot(x, x**2, label='quadratic')
plt.plot(x, x**3, label='cubic')

plt.xlabel('x label')
plt.ylabel('y label')

plt.title("Simple Plot")

plt.legend()

plt.show()
```


# 關於使用 pyplot 的 code style
可以簡單類似 matlab 的方式宣告，直接使用，非常方便

```
x = np.arange(0, 10, 0.2)
y = np.sin(x)
fig = plt.figure()
ax = fig.add_subplot(111)
ax.plot(x, y)
plt.show()
```
![](https://matplotlib.org/_images/sphx_glr_usage_004.png)

但在複雜與重複用的情境下，封裝成可重用的 function ，將 data 與 plot 部分拆開

```
def my_plotter(ax, data1, data2, param_dict):
    """
    A helper function to make a graph

    Parameters
    ----------
    ax : Axes
        The axes to draw to

    data1 : array
       The x data

    data2 : array
       The y data

    param_dict : dict
       Dictionary of kwargs to pass to ax.plot

    Returns
    -------
    out : list
        list of artists added
    """
    out = ax.plot(data1, data2, **param_dict)
    return out

# which you would then use as:

data1, data2, data3, data4 = np.random.randn(4, 100)
fig, ax = plt.subplots(1, 1)
my_plotter(ax, data1, data2, {'marker': 'x'})
```

有了以上的 functino 就可以輕鬆達到一下功能

```
fig, (ax1, ax2) = plt.subplots(1, 2)
my_plotter(ax1, data1, data2, {'marker': 'x'})
my_plotter(ax2, data3, data4, {'marker': 'o'})
```
# Backend 是什麼？

matplotlib 為了讓不同應用情境都能完成(EX: script, embed into GUI application)
將背後繪圖的苦工叫做 backend ，如底層繪圖 png. pdf 等等檔案格式處理，稱為 hardcopy backend，
或者是處理 interactive mode 的相關功能，成為 interactive backend

__Interactive v.s. non-interactive__

- interactive : 可以先動態用 .draw() 更新 figure 可以額外畫出新東西
- non-interactive : 全部一次畫完，最後用 .show() 呈現，無法額外改動

P.S. 通常都是你沒辦法正常會出圖片時，才會去深入研究如何設定

# Reference

- [Usage Guide — Matplotlib 2.1.0 documentation](https://matplotlib.org/tutorials/introductory/usage.html#sphx-glr-tutorials-introductory-usage-py)
- [Tutorials — Matplotlib 2.1.0 documentation](https://matplotlib.org/tutorials/index.html)