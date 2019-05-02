+++
author = "ykhorizon"
date = "2019-04-21T17:59:16+08:00"
title = "Windows 10 home 升級 pro 受難計"
categories = ['laptop']
tags = ['windows-10','lenovo']
type = "post"
+++

# 事出有因

當初在購買新的筆電時，迫於各種無奈之下，就挑選了 lenovo T480s 並安裝 windows 10，
但因為一時不察，想說應該安裝『家用版就足夠了』，必沒有遠端和加密的需求，當時也有看到微軟有自己的虛擬化 hyper-v ，想說 virtualbox 就足夠了，天知道買來用兩天就發現，要執行 docker 必須要專業版（對 hyper-v 有依賴）。這下驢了，當初只有加 1500元 就可買到專業版，這下必須花至少 3000元才能從家用版升級到專業版

# 波折

當時決定去一般零售店購買 window 10 專業版，就購買了專業版（隨機版，幫定電腦/筆電主機板，無法轉移授權到其他機器）
買回來發現直接輸入金鑰，竟然無效！求助 lenovo 客服、微軟客服、零售店的電腦專員，不是踢皮球，就是無法解決（備註：我滿感謝零售店的電腦專員，他們有認真幫我解決，雖然無效，但最終給了找出解答的方向）

# 解方

1. window鍵 + r ，輸入 CHANGEPK.exe ，開啟啟用頁面
2. 關閉任何網路連接(wifi、有線網路)，避免連上網路自動抓取家用版金鑰
3. 輸入 windows 專業版預設金鑰 VK7JG-NPHTM-C97JM-9MPGT-3V66T ，電腦會從『家用版』轉成『專業版』，但尚未啟用成功
4. 開啟網路連接
5. 這次輸入你的正版金鑰，並啟用
6. 最後檢查 Windows 版本

# 參考

- [FIX: WINDOWS 10 HOME TO PRO UPGRADE ERROR 0X803FA067](http://www.noelpulis.com/fix-windows-10-home-to-pro-upgrade-error-0x803fa067/)