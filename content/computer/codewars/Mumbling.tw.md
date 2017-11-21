+++
author = "ykhorizon"
date = "2017-10-26T20:23:11+08:00"
title = "[Codewars] Mumbling"
categories = ["programming","programming/codewars"]
topics = []
keywords = []
tags = ["C-sharp","kata"]
type = "post"

+++

# Outline
- [問題範例](#%E5%95%8F%E9%A1%8C%E7%AF%84%E4%BE%8B)
- [我的寫法](#%E6%88%91%E7%9A%84%E5%AF%AB%E6%B3%95)
- [他人解法賞析](#%E4%BB%96%E4%BA%BA%E8%A7%A3%E6%B3%95%E8%B3%9E%E6%9E%90)
- [比較差異](#%E6%AF%94%E8%BC%83%E5%B7%AE%E7%95%B0)
    - [LINQ](#linq)
    - [String.Join](#stringjoin)
    - [String.Select 與 lambda 運算式](#stringselect-%E8%88%87-lambda-%E9%81%8B%E7%AE%97%E5%BC%8F)

<!--more-->

# 問題範例

```c#
Accumul.Accum("abcd");    // "A-Bb-Ccc-Dddd"
Accumul.Accum("RqaEzty"); // "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
Accumul.Accum("cwAt");    // "C-Ww-Aaa-Tttt"
```

# 我的寫法

```c#
using System;

public class Accumul 
{

    // Version 1
    public static String Accum1(string s) 
  {
    string sOut = "";
     for(int i=0;i<s.Length;i++){
       
       char c = s[i]; // useless condition
       if(char.IsLower(s[i]) == true){
         c = char.ToUpper(s[i]);
       }
       sOut += c;
       for(int j=0;j<i;j++){
         sOut += char.ToLower(s[i]);
       }
       if(i!=s.Length-1){
         sOut += "-";
       }
     }
     return sOut;
  }
    // Version 2
  public static String Accum2(string s) 
  {
    string sOut = "";
     for(int i=0;i<s.Length;i++){
       
       sOut += char.ToUpper(s[i]);
       for(int j=0;j<i;j++){
         sOut += char.ToLower(s[i]);
       }
       if(i!=s.Length-1){
         sOut += "-";
       }
     }
     return sOut;
  }
}
}
```

# 他人解法賞析

```c#
using System;
using System.Linq;
public class Accumul 
{
  public static String Accum(string s) 
  {
     return string.Join("-",s.Select((x,i)=>char.ToUpper(x)+new string(char.ToLower(x),i)));
  }
}
```
# 比較差異
重點差異在 LINQ 可以節省很多時間，還有 lambda function 可以很簡短完成任務。

## LINQ
全名是 Language Integrated Query ，目的是希望 C# 能夠用 query 的方式處理資料(不管是SQL database,XML或其他Web)，直接看範例就能懂。

```c#
class LINQQueryExpressions
{
    static void Main()
    {
        
        // Specify the data source.
        int[] scores = new int[] { 97, 92, 81, 60 };

        // Define the query expression.
        IEnumerable<int> scoreQuery =
            from score in scores
            where score > 80
            select score;

        // Execute the query.
        foreach (int i in scoreQuery)
        {
            Console.Write(i + " ");
        }            
    }
}
// Output: 97 92 81
```
## String.Join
格式為: String.Join (String, String[])
基本上和 python 的 join 是一樣，將字串陣列用指定至串從中間串接起來。
[String.Join 方法 ](https://msdn.microsoft.com/zh-tw/library/57a79xd0(v=vs.110).aspx)

## String.Select 與 lambda 運算式

String.Select 是將 Enumerable 中每一個元素都執行過一次 lambda function。
字串string是有繼承 Enumerable ，因此可以被 iterate 過

簡單範例為下

```c#
IEnumerable<int> squares =
    Enumerable.Range(1, 10).Select(x => x * x);

foreach (int num in squares)
{
    Console.WriteLine(num);
}
/*
 This code produces the following output:

 1
 4
 9
 16
 25
 36
 49
 64
 81
 100
*/
```
[String.Select](https://msdn.microsoft.com/en-us/library/bb548891(v=vs.110).aspx)

他人解法中，這部分 
```c#
(x,i)=>char.ToUpper(x)+new string(char.ToLower(x),i) 
```
是使用 Lambda 運算式。格式為 (input-parameters) => { statement; } 是指將左邊傳入的參數，右邊是函式的運算
搭配 Linq 的 Select 可以使用 iterate value 和 index，因此這邊 x 是 string 中的 char，i 是 index。

- [Stack Overflow](https://stackoverflow.com/questions/4174701/lambda-expression-for-getting-indexes-of-list-items-conditionally)
- [Lambda 運算式, Lambda Expressions](https://docs.microsoft.com/zh-tw/dotnet/csharp/programming-guide/statements-expressions-operators/lambda-expressions)