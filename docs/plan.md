# Where's My Money? — 未來計畫

> 這份文件只放**還沒定案**的提案。提案定案後，從這裡移除，並把設計寫進 [spec.md](spec.md)；過程和完成的步驟記在 [CHANGELOG.md](CHANGELOG.md)。

## 技術方向（預設，開工前可再調整）

| 項目 | 選擇 |
|---|---|
| 語言 / UI | Kotlin + Jetpack Compose（Material 3） |
| 架構 | 單一 `app` module 起步，MVVM + 單向資料流（UI ← StateFlow ← ViewModel ← Repository） |
| 本機資料庫 | Room（SQLite），搭配 Coroutines / Flow |
| 設定值 | DataStore（Preferences） |
| 導覽 | Navigation Compose |
| 依賴注入 | Hilt |
| 建置 | Gradle Kotlin DSL + version catalog（`libs.versions.toml`），在 WSL 用 command-line Android SDK 建置 |
| 資料範圍 | 只存本機，不做帳號、不連網路 |
| Python | 不需要；之後若有輔助腳本再用 uv + Python 3.12 |

## Phase 0 — 專案初始化

- [ ] 決定 package name（`com.<name>.whereismymoney`）、minSdk、targetSdk
- [ ] 建立 Gradle 專案骨架、version catalog、`.gitignore`
- [ ] `git init`，第一個 commit
- [ ] 在 WSL 裝好 Android SDK command-line tools，確認 `./gradlew assembleDebug` 能過
- [ ] 確認裝到實機 / 模擬器的方式（WSL `adb` ↔ Windows）
- [ ] 基本的 lint / format 設定（ktlint 或 spotless）

## Phase 1 — MVP：能記帳

- [ ] **記一筆**：金額、收入 / 支出、分類、日期、備註
- [ ] **紀錄清單**：依日期分組，顯示每日小計
- [ ] **編輯 / 刪除**一筆紀錄
- [ ] **預設分類**（餐飲、交通、購物、娛樂、居住、醫療、薪資、其他…）
- [ ] **本月總覽**：本月收入、支出、結餘

## Phase 2 — 看懂錢去哪

- [ ] 統計頁：分類圓餅圖 / 長條圖、月份趨勢
- [ ] 依期間、分類、關鍵字篩選與搜尋
- [ ] 自訂分類（新增、改名、圖示 / 顏色、排序、封存）
- [ ] 多帳戶：現金、銀行、信用卡、電子支付，以及帳戶間轉帳

## Phase 3 — 管錢

- [ ] 每月預算（總預算 + 分類預算），超支提醒
- [ ] 週期性紀錄（訂閱、房租等自動產生）
- [ ] 匯出 / 匯入 CSV
- [ ] 本機備份與還原（匯出資料庫檔到使用者選的位置）

## Phase 4 — 打磨

- [ ] 深色模式 / Material You 動態配色
- [ ] 桌面小工具（快速記帳、本月支出）
- [ ] 快速記帳捷徑（通知列或 App Shortcut）
- [ ] App 鎖（生物辨識 / PIN）
- [ ] 多幣別

## 待決定的問題

- 金額存法：建議用 `Long` 存最小貨幣單位（TWD 就是「元」），不要用 `Double`，以免浮點誤差
- 預設幣別：TWD？
- 一週從星期一還是星期日開始？月結日要不要可以自訂（例如信用卡結帳日）？
