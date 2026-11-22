# Changelog

這份文件記錄每次版本更新的修改內容。

- 格式參考 [Keep a Changelog](https://keepachangelog.com/zh-TW/1.1.0/)
- 版本號遵循 [語意化版本](https://semver.org/lang/zh-TW/)，對應 Android 的 `versionName`
- 分類：`Added` 新增、`Changed` 變更、`Fixed` 修正、`Removed` 移除

## [Unreleased]

### Added

- 建立專案文件：`plan.md`、`spec.md`、`CHANGELOG.md`
- 在 `spec.md` 最上方加入專案規則
- 新增 `git-style.md` commit 訊息規範（不含 `[Auto]` tag）
- 新增 `CLAUDE.md`，要求每次實作前先讀 `spec.md` 與 `git-style.md`

### Changed

- `spec.md` 的「已完成功能」改為「目前設計」，`plan.md` 開頭說明改為只放未定案提案，配合專案規則第 2、4 條
- `plan.md` 改為完整功能 checklist（A–K），標出第一批：A1、A2、B1、B2、B3、C1、C2
- 決定金額用 `Long`、幣別 TWD、一週起始日由使用者選擇，寫入 `spec.md`
- 建立 git repo，連結 GitHub remote
