# line-ecard-relay-l2

本 repo 服務 **L2/L3 客戶**，使用**獨立的 LIFF app**（LIFF ID：待建立後填入）。

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

L1 凍結版請見 `../relay/README-L1-FROZEN.md`。
