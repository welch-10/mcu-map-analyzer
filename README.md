# MCU Map Analyzer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Platform](https://img.shields.io/badge/platform-browser-brightgreen)
![Compilers](https://img.shields.io/badge/compilers-CC--RL%20%7C%20CA78K0R-orange)
![Languages](https://img.shields.io/badge/i18n-14%20languages-blueviolet)
![No Dependencies](https://img.shields.io/badge/dependencies-none-success)

> 🌐 **[English README](README.en.md)** | このページは日本語

ルネサス RL78 ファミリ用の **mapファイル可視化ツール**。CC-RL / CA78K0R が出力する map ファイルから、ROM 使用率・ファイル別内訳・メモリ配置・ミラー領域の使用状況・差分比較などを直感的に確認できます。

ブラウザだけで動作する **1ファイル HTML** なので、配布も実行も簡単です。サーバ通信ゼロ、依存ライブラリゼロ。

🌐 **デモ** ▶ [https://welch-10.github.io/mcu-map-analyzer/](https://welch-10.github.io/mcu-map-analyzer/)

---

## ✨ 特徴

- 📦 **1ファイル配布** — `MCUMapAnalyzer.html` を開くだけ。サーバ・インストール・ビルド不要
- 🔒 **完全オフライン動作** — ファイルはローカルで解析。サーバへの送信は一切なし
- 🌐 **14 言語対応** — 日本語 / English / 简体中文 / 繁體中文 / 한국어 / Tiếng Việt / ไทย / Bahasa Indonesia / Français / Italiano / Español / Português / Polski / Deutsch
- 🔢 **ロケール対応の数値表記** — `1.234,56` (ドイツ・伊・西・葡・蘭) / `1 234 567` (仏・波) / `1,234.56` (英・日・中・韓・タイ) を自動切替
- 📱 **モバイル対応** — Android Chrome / iOS Safari でも動作
- 🎨 **直感的UI** — ROM 使用状況の俯瞰、メモリ配置の可視化
- 🔍 **メモリマップのインタラクティブ操作** — Alt+ホイールでマウスカーソル追従ズーム、ホバーでファイル名表示
- 🪞 **ミラー領域の使用状況可視化** — RL78 固有のハードウェアミラー領域に何 KB 詰まっているかを 1 画面で確認
- ⚖️ **差分比較** — 2つの map ファイルを並べてビルド前後の変化を確認
- 🧪 **サンプルファイル解析** — GitHub Pages 版なら 1 クリックで匿名化サンプル(RL78/G23 384KB品)を試用可能

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

### 方法1: ブラウザから直接（GitHub Pages、おすすめ）

[https://welch-10.github.io/mcu-map-analyzer/](https://welch-10.github.io/mcu-map-analyzer/) を開いて map ファイルを投入。

ボタン「**サンプルファイルを解析**」で匿名化済みサンプルを 1 クリックで試用可能（GitHub Pages 版のみ）。

### 方法2: ローカルで使う

1. [Releases](../../releases) から最新の `MCUMapAnalyzer.html` をダウンロード
2. ブラウザで開く（社内 LAN/オフライン環境でも動作）
3. map ファイルをドラッグ&ドロップ または「ファイルを選択」で投入

> ファイルはブラウザ内でのみ処理され、サーバへの送信はありません。

## 🌍 動作環境

| ブラウザ | 最小バージョン | 備考 |
|---|---|---|
| Chrome / Edge | 90+ | 2021年4月～ |
| Firefox | 103+ | 2022年7月～ (backdrop-filter 対応) |
| Safari | 16+ | 2022年9月～ (`:has()` / `replaceChildren()` 対応) |
| Android Chrome | 90+ | モバイル対応 |
| iOS Safari | 16+ | モバイル対応 |

## 📊 解析機能

### 概要 (Overview)
- ROM 使用率の俯瞰（容量・残量・使用率・KPI カード）
- カテゴリ別内訳ドーナツ（コード/定数/RFD/その他Lib/システム の 5 分類）
- **ハードウェアミラー領域カード** — 領域範囲・サイズ・ミラー元物理アドレス・MAA バンク推定を表示

### ファイル別 (By File)
- ファイル単位のサイズと使用率
- カテゴリの内訳を積み上げグラフで表示
- ファイル名検索・カテゴリフィルタ
- ROM 使用率テーブル（列ヘッダクリックでソート）
- CSV 出力（フィルタ反映、英数値固定で Excel パース安定）

### メモリマップ (Memory Map)
- ROM 領域全体のセクション配置を可視化（仮想スクロールで数千〜数万行も軽快）
- カテゴリ別 / ファイル別の色分け切替
- 行幅切替（自動 / 32B/行 〜 256KB/行）
- **Alt+ホイールでマウスカーソル追従ズーム**
- **マウスホバーでファイル名ツールチップ**
- セクション検索・選択ピン留め (Esc で解除)
- **ミラー元領域オーバーレイ** — 物理 ROM のうち F 領域からも読める範囲を斜線で表示

### 比較 (Compare)
- 2 つの map ファイルを並べて差分計算
- カテゴリ別差分サマリ（5 分類それぞれの増減）
- ファイル別差分テーブル（増加/減少/追加/削除/変化なし のバケット分類）
- 比較不可ケースの自動検出（コンパイラ違い・デバイス違い・ROM 容量違い・共通ファイル比率低下）
- 差分 CSV 出力

### rawデータ (Raw Data)
- セクション別総サイズ表
- ファイル × セクション の内訳マトリクス

## 🤝 コントリビューション

バグ報告・機能要望・プルリクエスト歓迎します。

- [Issue](../../issues) でバグや機能要望を投稿
- [Discussions](../../discussions) で雑談・質問
- [CONTRIBUTING.md](CONTRIBUTING.md) を参照のうえ Pull Request

特に歓迎する貢献:
- **CC-RX / CC-RH パーサ実装**
- 新しい RL78 シリーズの DeviceDB 追加
- 翻訳の改善・新規言語追加
- スクリーンショット撮影

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
