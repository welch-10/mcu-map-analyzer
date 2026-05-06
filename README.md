# MCU Map Analyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-browser-brightgreen)
![Compilers](https://img.shields.io/badge/compilers-CC--RL%20%7C%20CA78K0R-orange)
![No Dependencies](https://img.shields.io/badge/dependencies-none-success)

ルネサス RL78 ファミリ用の **mapファイル可視化ツール**。CC-RL / CA78K0R が出力するmapファイルから、ROM使用率・ファイル別内訳・メモリ配置・差分比較などを直感的に確認できます。

ブラウザだけで動作する **1ファイル HTML** なので、配布も実行も簡単です。サーバ通信ゼロ、依存ライブラリゼロ。

🌐 **デモ** ▶ [https://welch-10.github.io/mcu-map-analyzer/](https://welch-10.github.io/mcu-map-analyzer/)

---

## ✨ 特徴

- 📦 **1ファイル配布** — `MCUMapAnalyzer.html` を開くだけ。サーバ・インストール・ビルド不要
- 🔒 **完全オフライン動作** — ファイルはローカルで解析。サーバへの送信は一切なし
- 🌐 **i18n対応** — 日本語 / 英語の切替可能
- 📱 **モバイル対応** — Android Chrome / iOS Safari でも動作
- 🎨 **直感的UI** — ROM使用状況の俯瞰、メモリ配置の可視化
- ⚖️ **差分比較** — 2つのmapファイルを並べてビルド前後の変化を確認

## 🛠 対応コンパイラ

| コンパイラ | ステータス | 備考 |
|---|---|---|
| **CC-RL** | ✅ Supported | RL78用、Renesas Optimizing Linker (rlink) |
| **CA78K0R** | ✅ Supported | RL78/78K0R用、78K0R Linker |
| CC-RX | 🔍 Detected only | 検出のみ実装、パーサ未実装 |
| CC-RH | 🔍 Detected only | 検出のみ実装、パーサ未実装 |

## 📋 対応形式

- 拡張子: `.map` / `.map.txt` / `.lis`
- 最大サイズ: 20 MB
- 文字コード: UTF-8 / Shift_JIS（自動判別）

## 🚀 使い方

### 方法1: ローカルで使う（推奨）

1. [Releases](../../releases) から最新の `MCUMapAnalyzer.html` をダウンロード
2. ブラウザで開く
3. mapファイルをドラッグ&ドロップ または「ファイルを選択」で投入

### 方法2: ブラウザから直接（GitHub Pages）

[https://welch-10.github.io/mcu-map-analyzer/](https://welch-10.github.io/mcu-map-analyzer/) を開いてmapファイルを投入

> ファイルはブラウザ内でのみ処理され、サーバへの送信はありません。

## 🖼 スクリーンショット

| 概要画面 | メモリマップ | 差分比較 |
|---|---|---|
| ![overview](docs/screenshots/overview.png) | ![memmap](docs/screenshots/memmap.png) | ![compare](docs/screenshots/compare.png) |

(スクリーンショット差し替え予定)

## 🌍 動作環境

| ブラウザ | 最小バージョン | 備考 |
|---|---|---|
| Chrome / Edge | 90+ | 2021年4月～ |
| Firefox | 103+ | 2022年7月～ (backdrop-filter対応) |
| Safari | 16+ | 2022年9月～ (`:has()` / `replaceChildren()` 対応) |
| Android Chrome | 90+ | モバイル対応 |
| iOS Safari | 16+ | モバイル対応 |

## 📊 解析機能

### 概要 (Overview)
- ROM使用率の俯瞰（容量・残量・使用率）
- カテゴリ別内訳（コード/定数/RFD/その他Lib/システム の5分類）
- ハードウェアミラー領域情報（RL78固有）

### ファイル別 (By File)
- ファイル単位のサイズと使用率
- カテゴリの内訳を積み上げグラフで表示
- ファイル名検索・カテゴリフィルタ
- CSV出力

### メモリマップ (Memory Map)
- ROM領域全体のセクション配置を可視化
- カテゴリ別 / ファイル別の色分け切替
- 行幅切替（自動 / 32B/行 ～ 256KB/行）
- セクション検索・ピン留め
- ミラー元領域のオーバーレイ表示

### 比較 (Compare)
- 2つのmapファイルを並べて差分計算
- カテゴリ別の差分サマリ
- ファイル別差分（増加/減少/追加/削除/変化なし のバケット分類）
- 差分CSV出力

### rawデータ (Raw Data)
- セクション別総サイズ表
- ファイル × セクション の内訳マトリクス

## 🤝 コントリビューション

バグ報告・機能要望・プルリクエスト歓迎します。

- [Issue](../../issues) でバグや機能要望を投稿
- [CONTRIBUTING.md](CONTRIBUTING.md) を参照のうえ Pull Request

## 📝 変更履歴

[CHANGELOG.md](CHANGELOG.md) を参照

## ⚖ License

[MIT License](LICENSE)

Copyright (c) 2026 ウェルチ

商用利用・個人利用ともに許可されていますが、**無保証** (`AS IS`) です。
本ツールの使用に起因する損害について、作者は一切の責任を負いません。

## 📑 商標 / Trademarks

CC-RL, CC-RX, CC-RH, CA78K0R, RL78 はルネサス エレクトロニクス株式会社の商標または登録商標です。
本ツールはルネサス エレクトロニクス株式会社の製品ではなく、同社の公認・支援を受けたものでもありません。

CC-RL, CC-RX, CC-RH, CA78K0R, and RL78 are trademarks or registered trademarks
of Renesas Electronics Corporation. This tool is not a Renesas Electronics
product and is not affiliated with or endorsed by Renesas Electronics
Corporation.
