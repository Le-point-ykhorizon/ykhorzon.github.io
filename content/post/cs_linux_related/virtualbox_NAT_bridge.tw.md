+++
author = "ykhorizon"
date = "2017-11-17T16:57:00+08:00"
title = "virtualbox 網路設定 NAT v.s. Bridge mode"
categories = ["virtualbox","virtualbox/network"]
topics = []
keywords = []
tags = ["network"]
type = "post"
+++

# Outline

- [Scenario](#scenario)
- [什麼是 NAT, Bridge 和 Host-Only?](#%E4%BB%80%E9%BA%BC%E6%98%AF-nat-bridge-%E5%92%8C-host-only)
- [延伸問題：192.168.xxx.xxx 和 172.16.xxx.xxx 是什麼東西，代表什麼意義？](#%E5%BB%B6%E4%BC%B8%E5%95%8F%E9%A1%8C%EF%BC%9A192168xxxxxx-%E5%92%8C-17216xxxxxx-%E6%98%AF%E4%BB%80%E9%BA%BC%E6%9D%B1%E8%A5%BF%EF%BC%8C%E4%BB%A3%E8%A1%A8%E4%BB%80%E9%BA%BC%E6%84%8F%E7%BE%A9%EF%BC%9F)
- [推論一下，我的問題是什麼？](#%E6%8E%A8%E8%AB%96%E4%B8%80%E4%B8%8B%EF%BC%8C%E6%88%91%E7%9A%84%E5%95%8F%E9%A1%8C%E6%98%AF%E4%BB%80%E9%BA%BC%EF%BC%9F)

<!--more-->

# Scenario
在使用 virtualbox 作為開發環境時，需要由外部 internet 聯絡 virtualbox 內部的 guest OS，使用 Networking Adapter 預設為 NAT ，無法滿足這個需求(需要倚靠 port forwarding)


# 什麼是 NAT, Bridge 和 Host-Only?

我收集一些網路上的資料，統整了一下

- [Differences between bridged and NAT networking](https://serverfault.com/questions/490043/differences-between-bridged-and-nat-networking)
- [NAT vs. bridged network: A simple diagram](http://techgenix.com/nat-vs-bridged-network-a-simple-diagram-178/)

![](http://www.virtualizationadmin.com/lowe/wp-content/blogs/60/files/2011/11/image2.png)


Host-only only permits network operations with the Host OS.

NAT mode will mask all network activity as if it came from your Host OS, although the VM can access external resources.

Bridged mode replicates another node on the physical network and your VM will receive it's own IP address if DHCP is enabled in the network.

# 延伸問題：192.168.xxx.xxx 和 172.16.xxx.xxx 是什麼東西，代表什麼意義？
內網的虛擬IP

- [問：何謂『虛擬 IP 』，與『實體 IP 』或者『固定 IP 』『動態 IP 』有啥不同？ 192.169.x.x](http://linux.vbird.org/problem/linux/problem_1.php)

# 推論一下，我的問題是什麼？
學校給我的是實體 IP，為 140.114.xxx.xxx，實驗的 switch 應該沒開什麼特殊功能，沒有切分內網
我的主機直接套用的就是__實體IP__，根本就不存在內網。
理論上一般家庭或公司，對外的實體IP只會有一個，內部其他電腦或連線都是虛擬IP，會是 192.168.xxx.xxx

