# Changelog

このプロジェクトの主要な変更履歴。
[Keep a Changelog](https://keepachangelog.com/ja/1.1.0/) の形式に従い、
[Semantic Versioning](https://semver.org/lang/ja/) を採用しています。

## [Unreleased]

## [1.1.0] - 2026-05-10

### Added
- 多言語対応を 14 言語に拡張: 简体中文 / 繁體中文 / 한국어 / Tiếng Việt / ไทย / Bahasa Indonesia / Français / Italiano / Español / Português / Polski / Deutsch
- ロケール対応の数値整形 (`Util.fmtFixed/fmtFloat/fmtKB/fmtNumber` を `toLocaleString` ベースに改修。ドイツ語の `1.234,56` 等に追従)
- メモリマップで **Alt+ホイールのマウスカーソル追従ズーム**
- メモリマップで **ファイル名のホバーツールチップ**
- welcome 画面に **「サンプルファイルを解析」ボタン** (GitHub Pages 版のみ表示)
- 匿名化済みサンプル map ファイル `docs/samples/sample_ccrl.map` をリポジトリに追加 (RL78/G23 384KB品)
- `LANG_DEFS` による言語定義の単一情報源化
- `README.en.md` (English README)

### Fixed
- メモリマップ拡大時に固定ツールチップが画面外にスクロールしてしまう問題 (pin tooltip の親要素を `.card` に変更)
- 解析後画面で言語切替しても日本語が残る複数箇所 (device-bar / KPI / mirror カード / compare 画面 等)
- FOUS (Flash of Unwanted State): 初回ロード時に「読み込み後の画面」が一瞬見える問題
- index.html リダイレクト時のフラッシュ
- RL78/G12 12KB / 16KB ミラーDB の lower/upper/sizeKB 欠落
- ROM 容量フォールバックで使用率 100% 超え表示が出るバグ
- サンプル解析時にカテゴリ分類が崩れていた問題 (匿名化スクリプトを分類保存型に改修)

### Changed
- `Util.fmtPct` を `Util.fmtFixed` にリネーム (用途の明確化)
- 商標表記に CC-RX / CC-RH を追加
- README をモバイル機能の前面アピールから外す調整 (動作はするが PC 利用前提)

## [1.0.0] - 2026-05-04

### Added
- 初回公開
- CC-RL / CA78K0R 対応の mapファイル解析
- ROM使用率 / カテゴリ別内訳 / ファイル別内訳の可視化
- メモリマップ表示（仮想スクロール、検索フィルタ、ピン留め対応）
- 2つのmapファイルの差分比較
- ハードウェアミラー領域情報（RL78固有）
- rawデータ表示
- i18n対応（日本語 / 英語）
- モバイル対応（Android Chrome / iOS Safari）
- CSV出力（ファイル別、差分）
- CC-RX / CC-RH の検出（パーサ未実装）

### Notes
- ライセンス: MIT
- 単一HTML配布（依存ライブラリなし、サーバ通信なし）

[Unreleased]: https://github.com/welch-10/mcu-map-analyzer/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/welch-10/mcu-map-analyzer/releases/tag/v1.1.0
[1.0.0]: https://github.com/welch-10/mcu-map-analyzer/releases/tag/v1.0.0
