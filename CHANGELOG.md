# Changelog

このプロジェクトの主要な変更履歴。
[Keep a Changelog](https://keepachangelog.com/ja/1.1.0/) の形式に従い、
[Semantic Versioning](https://semver.org/lang/ja/) を採用しています。

## [Unreleased]

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

[Unreleased]: https://github.com/welch-10/mcu-map-analyzer/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/welch-10/mcu-map-analyzer/releases/tag/v1.0.0
