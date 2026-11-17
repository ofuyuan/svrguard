# SvrGuard

**主機入侵偵測與自動封鎖：SSH 暴力破解、網站掃描、異常程式執行**

[English](README.md) · [官網](https://svrguard.ofuyuan.com/zh/) · [下載](https://svrguard.ofuyuan.com/zh/download.html) · [功能](https://svrguard.ofuyuan.com/zh/features.html) · [更新紀錄](https://svrguard.ofuyuan.com/zh/release.html) · [論壇](https://forum.ofuyuan.com/)

為同時照顧多台主機的接案者、小團隊與 NAS 用戶而做。

> 這個 repo 用來放專案說明與收集回饋，不含原始碼。

![三層安全保護循環](https://svrguard.ofuyuan.com/images/three_layer_loop_ring_zh.png)

## 三層安全保護循環

透過三層防護機制，由分析系統日誌、異常程式檢查及資源異常管理，3 個面向來保護你主機的安全，免於受到威脅。

- **第一層：分析系統日誌** —— 分析網站與 SSH 的日誌，判定為攻擊就寫進系統防火牆。規則內建，不必自己寫正規表達式；每一筆封鎖都看得到是哪條規則、哪幾行 log。
- **第二層：異常程式檢查** —— 每次檢查都看入侵者常留下的痕跡：開機自動執行的後門、從暫存或隱藏目錄執行的程式、被加料的預載函式庫、登入失敗多次之後的密碼登入成功、主機主動連到挖礦池。發現就寄通知，由你決定怎麼處理。
- **第三層：資源異常管理** —— 持續看 CPU、記憶體、磁碟。被偷偷拿去挖礦或塞滿磁碟時，超過門檻就通知你，和攻擊通知走同一條管道。

## 安裝

```sh
curl -fsSL https://svrguard.ofuyuan.com/install.sh | sudo sh
```

這一行適用 Linux 與 macOS（Apple Silicon）。Synology NAS 請改到[下載](https://svrguard.ofuyuan.com/zh/download.html)頁安裝 DSM 套件；deb／rpm／tar.gz 安裝包也在那一頁。各平台能讀哪些日誌見[功能](https://svrguard.ofuyuan.com/zh/features.html)。

## 畫面

![攻擊地圖](https://svrguard.ofuyuan.com/images/attack-map.png)

![本機儀表板](https://svrguard.ofuyuan.com/images/dashboard.png)

![Hub：多台主機一個畫面](https://svrguard.ofuyuan.com/images/fleet.png)

## 裝上之後，你得到什麼

- **規則內建，不必自己寫** —— 不用維護正規表達式；判定為攻擊就寫進系統防火牆，完全不連外的主機也照常運作。
- **每一筆封鎖都有事證** —— 看得到是哪條規則、哪幾行 log；誤判時可以自己解除封鎖或加白名單。
- **封鎖沒生效會告訴你** —— 防火牆寫不進去時主控台會顯示，連續失敗會寄 Email，不會靜靜失效。
- **日誌留在你的主機** —— 分析在本機完成；加入 Hub 後只送被判定為攻擊的那幾行當事證。不看網站內容、不側錄訪客，與 Hub 的連線一律由這台機器主動發起。

## 問題與回饋

請到[論壇](https://forum.ofuyuan.com/)發問。歷次更新見[更新紀錄](https://svrguard.ofuyuan.com/zh/release.html)。
