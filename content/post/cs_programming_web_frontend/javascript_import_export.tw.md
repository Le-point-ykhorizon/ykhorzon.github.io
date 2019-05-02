+++
author = "ykhorizon"
date = "2019-04-04T00:25:56+08:00"
title = "Javascript 中 Import 和 Export"
categories = []
tags = ["ES6","javascript","fundamental"]
type = "post"
+++

# default

# named

named import 的意思是指『export 時的 variable/function 已經被命名，無法在 import 時重新取名』;如果在 import 時改名將會有 error ，確保 variable/function 保持原本的名字。

> Named exports are useful to export several values. During the import, it is mandatory to use the same name of the corresponding object.

{{< highlight javascript "linenos=table">}}
// utility.js
function parseLogs() {
// implementation
}
function generateLogs() {
// implementation
}
export { parseLogs, generateLogs };

// main.js
import { parseLogs, generateLogs } from "utility";
parseLogs();

{{< / highlight  >}}

# 心得

當在寫單元測試(e.g Jest)

# References

- [MDN, import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import)
- [MDN, export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export)
