+++
author = "ykhorizon"
date = "2018-06-18T09:44:21+08:00"
title = "LeetCode 728.Self Dividing Numbers"
categories = ["programming","programming/leetcode"]
topics = []
keywords = []
tags = ["leetcode","math"]
type = "post"
draft = true
+++

# 728. Self Dividing Numbers 

## Description 

A self-dividing number is a number that is divisible by every digit it contains.
For example, 128 is a self-dividing number because 128 % 1 == 0, 128 % 2 == 0, and 128 % 8 == 0.
Also, a self-dividing number is not allowed to contain the digit zero.
Given a lower and upper number bound, output a list of every possible self dividing number, including the bounds if possible. 

## Input 
left = 1, right = 22
(The boundaries of each input argument are 1 <= left <= right <= 10000.)

## Output 
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 15, 22]

# My solution ver1

<pre>
<code>
import math
class Solution:
    def selfDividingNumbers(self, left, right):
        """
        :type left: int
        :type right: int
        :rtype: List[int]
        """
        init_value = left
        resList = []
        while init_value <= right :
            
            # methdo 1
            # print(init_value)
            
            v = init_value
            v = str(v)
            digitsList = [c for c in v]
            # print(digitsList)
            
            digitDividedFlag = True
            for d in digitsList:
                if int(d) != 0 and init_value % int(d) == 0:
                    digitDividedFlag &= True
                else:
                    digitDividedFlag &= False
            if digitDividedFlag:        
                resList.append(init_value)
            
            # increase
            init_value += 1
        
        return resList
</code>
</pre>


> Although my solution is correct...
> The performance of my solution is poor(only beat 12% other performance), so I need to improve my code!

![](/content_img/728_Self_Dividing_Numbers/perf.png)


# Complexity Analysis

<pre>
<code>
import math
class Solution:
    def selfDividingNumbers(self, left, right):
        """
        :type left: int
        :type right: int
        :rtype: List[int]
        """
        init_value = left
        resList = []
        <span style="color:red">
        while init_value <= right :
        </span>
            
            # methdo 1
            # print(init_value)
            
            v = init_value
            v = str(v)
            <span style="color:red">
            digitsList = [c for c in v]
            </span>
            # print(digitsList)
            
            digitDividedFlag = True
            for d in digitsList:
                if int(d) != 0 and init_value % int(d) == 0:
                    digitDividedFlag &= True
                else:
                    digitDividedFlag &= False
            if digitDividedFlag:        
                resList.append(init_value)
            
            # increase
            init_value += 1
        
        return resList
</code>
</pre>

Assume the n = left - right
x : average digits per number
O(n) = n ( x + x () )
what is the time complexity of list append ?