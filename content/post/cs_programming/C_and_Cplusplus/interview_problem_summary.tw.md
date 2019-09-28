+++
author = "ykhorizon"
date = "2018-12-23T08:47:03+08:00"
title = "[持續更新] C/C++ 常見面試問題統整"
categories = ["programming/CandC++","programming"]
tags = ["interview"]
type = "post"

+++

本文章有，共同編輯與時常更新的版本，會寫在 hackmd 上面

- https://hackmd.io/pWi7pgvISWSSjZN0HOYLGg


# C 語言

## Pointer

### Pointer of variable

- A variable hold the address (一個指向某個儲存位址的變數)

Example:

```C
    int val = 10;
    int * prt = &val
```

詳細可以參考 Mr. Open Gate 的文章 [C/C++ - 常見 C 語言觀念題目總整理（適合考試和面試）](http://mropengate.blogspot.com/2017/08/cc-c.html)

### Array and Pointer 的關係

在 C 語言中，處理字串一定會牽扯到 char pointer ，在基礎處理上要很注意

- https://www.geeksforgeeks.org/difference-pointer-array-c/
- https://www.geeksforgeeks.org/pointer-vs-array-in-c/

### Function Pointer
    
- 設計目的：
    - can be used to simplify code by providing a simple way to select a function to execute based on run-time values. [Function Pointer, wiki](https://en.wikipedia.org/wiki/Function_pointer)

## 變數範圍 Variable scope 和 生命週期 Variable life time 

- 常見有 local, static, global 
被宣告為 static 的 variable 有效的生命週期是『只要在程式還在執行都可以使用』，範圍只有在宣告的區域（Ex: function) 才能被存取

詳細可以參考 [Scope and Lifetime of Variables in C](https://blog.feabhas.com/2010/09/scope-and-lifetime-of-variables-in-c/)

## Declaration and Definition 差別


## 記憶體配置 Memory allocation
	
請參考 Mr. Open Gate 的文章 [C/C++ - 常見 C 語言觀念題目總整理（適合考試和面試）] 的 [用心去感覺] 記憶體的配置


## Struct Memory with Compiler Optimization

<iframe src="//www.slideshare.net/slideshow/embed_code/key/gDVgIO0rg38cDQ?startSlide=203" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/olvemaudal/deep-c" title="Deep C" target="_blank">Deep C</a> </strong> from <strong><a href="//www.slideshare.net/olvemaudal" target="_blank">Olve Maudal</a></strong> </div>

## Source code 如何被 compile 成執行檔

可以參考一下投影片『How A Compiler Works: GNU Toolchain』，至少有概念就好(p9~p14)

<iframe src="//www.slideshare.net/slideshow/embed_code/key/pIAwbkbnVdXxBY" width="595" height="485" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/jserv/how-a-compiler-works-gnu-toolchain" title="How A Compiler Works: GNU Toolchain" target="_blank">How A Compiler Works: GNU Toolchain</a> </strong> from <strong><a href="https://www.slideshare.net/jserv" target="_blank">Jim Huang</a></strong> </div>


# C++ Object-Oriented Programming

## Encapsulation

Access modifier

 - public
 - private
 - protect: can be access by derived class


## Inheritance

## Polymorphism

- virtual function

[Commonly Asked OOP Interview Questions | Set 1](https://www.geeksforgeeks.org/commonly-asked-oop-interview-questions/)

# Main References

- Interview Problems
    - [C/C++ - 常見 C 語言觀念題目總整理（適合考試和面試）](http://mropengate.blogspot.com/2017/08/cc-c.html)
	- https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/
	- https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/

- Reading Material
	- [Deep C (and C++), 強烈推薦](https://www.slideshare.net/olvemaudal/deep-c)
		

- Tutorial Material
    - https://www.learn-c.org/
	- https://beginnersbook.com/2014/01/c-tutorial-for-beginners-with-examples/



