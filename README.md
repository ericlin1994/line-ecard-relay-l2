# line-ecard-relay-l2

本 repo 服務 **L2/L3 客戶**，使用**獨立的 LIFF app**（LIFF ID：`2011946176-OWaDN0zD`）

- LIFF URL：`https://liff.line.me/2011946176-OWaDN0zD`
- Endpoint URL：`https://ericlin1994.github.io/line-ecard-relay-l2/`
- GitHub repo：`ericlin1994/line-ecard-relay-l2`（public，Pages 已啟用）
- 與 L1 的 LIFF `2011946176-a2549LFU` 在同一個 LINE Login channel（`2011946176`）底下；Scopes 只勾 `profile`

**目前狀態**：`TRACK_API` 尚未設定，追蹤只導向、不記錄。等 Apps Script 後端建好後，要用下列指令重建並重新推送：
```
TRACK_API=<後端網址> RELAY_LIFF_ID=2011946176-OWaDN0zD python relay/build_relay.py --tier L2
```。

## ⚠️ 絕對禁止
**不可以**把本 repo 的內容推到 `line-ecard-relay`——那是 L1 客戶正在使用的線上 repo。
本目錄目前沒有任何 remote；請只對 `line-ecard-relay-l2` 設定 remote。

## 重建方式
```
python relay/build_relay.py --tier L2
```
然後把 `relay/dist-l2/` 的內容複製到本目錄（`index.html`）。
靜態資產（`.nojekyll`、`og.jpg`、`privacy.html`）來自 `relay/`。

## 建立新 LIFF app 之後
用新的 LIFF ID 重建：
```
RELAY_LIFF_ID=<新ID> python relay/build_relay.py --tier L2
```
（PowerShell：`$env:RELAY_LIFF_ID="<新ID>"; python relay/build_relay.py --tier L2`）

## apps-script.txt（手機取得設定程式碼用）
`apps-script.txt` 是 `backend/apps-script.gs` 的純文字副本，供沒有電腦的情況下在手機瀏覽器全選複製，貼進 `script.google.com` 的獨立指令碼：
`https://raw.githubusercontent.com/ericlin1994/line-ecard-relay-l2/main/apps-script.txt`

內容不含任何機密（`OP_KEY` 為空字串、沒有金鑰或 token），刻意公開。修改 `backend/apps-script.gs` 後需同步更新此檔。

L1 凍結版請見 `../relay/README-L1-FROZEN.md`。
