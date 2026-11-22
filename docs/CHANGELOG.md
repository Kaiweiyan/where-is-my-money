# Changelog

這份文件記錄每次版本更新的修改內容。

- 格式參考 [Keep a Changelog](https://keepachangelog.com/zh-TW/1.1.0/)
- 版本號格式 `X.Y.Z`，對應 Android 的 `versionName`：
  - `X` 正式版（`0` 代表還沒正式發布）
  - `Y` 大改動
  - `Z` 小改動
- 每個版本在 git 打上 `vX.Y.Z` tag
- 分類：`Added` 新增、`Changed` 變更、`Fixed` 修正、`Removed` 移除

## [Unreleased]

## [0.1.0] - 2026-11-22

專案規劃版本：建立文件與規則，完成第一批功能設計，還沒有程式碼。

### Added

- 建立專案文件：`plan.md`、`spec.md`、`CHANGELOG.md`
- 在 `spec.md` 最上方加入專案規則
- 新增 `git-style.md` commit 訊息規範（不含 `[Auto]` tag）
- 新增 `CLAUDE.md`，要求每次實作前先讀 `spec.md` 與 `git-style.md`
- 以 HTML 可點擊雛形確認第一批設計，並把資料模型、首頁、記帳頁、分類管理、預設分類寫入 `spec.md`

### Changed

- `spec.md` 的「已完成功能」改為「目前設計」，`plan.md` 開頭說明改為只放未定案提案，配合專案規則第 2、4 條
- `plan.md` 改為完整功能 checklist（A–K），標出第一批：A1、A2、B1、B2、B3、C1、C2
- 決定金額用 `Long`、幣別 TWD、一週起始日由使用者選擇，寫入 `spec.md`
- 第一批功能從 `plan.md` 移到 `spec.md`
- 建立 git repo，連結 GitHub remote
