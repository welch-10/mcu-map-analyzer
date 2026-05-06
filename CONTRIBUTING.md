# Contributing to MCU Map Analyzer

ご関心ありがとうございます！バグ報告・機能要望・プルリクエスト歓迎します。

## バグ報告 / 機能要望

[Issue](../../issues) を立ててください。テンプレートが用意されています。

### バグ報告に含めてほしい情報
- 使用ブラウザ・OS
- 期待した動作 / 実際の動作
- 再現手順
- 可能であればmapファイルの該当箇所（機密に注意）またはサンプル

### 機能要望のヒント
- なぜその機能が必要か（解決したい問題）
- 想定される使い方
- 既存機能との関係

## Pull Request

### 開発の進め方

1. リポジトリをFork
2. featureブランチを作成（例: `feature/add-rx-parser`、`fix/memmap-scroll`）
3. 変更をコミット（[コミットメッセージ規約](#コミットメッセージ規約)を参照）
4. Pull Requestを作成

### 開発上の注意

本ツールは **1ファイルHTML配布** が基本要件です。
ビルドツールやnpm依存を増やす変更は受け入れにくいので、事前にIssueで相談ください。

#### コードスタイル
- インデント: スペース2
- ファイル末尾に改行
- 既存コードのレイヤー構造（Layer 0〜7）を維持
- グローバル汚染を避け、適切なモジュールに集約

#### 動作確認
- Chrome / Firefox / Safari の最新版で確認
- モバイル（Android / iOS）でも確認できると望ましい
- `node make_demo_*.cjs` でデモファイル生成・動作確認

### コミットメッセージ規約

簡易の[Conventional Commits](https://www.conventionalcommits.org/ja/v1.0.0/) を推奨：

```
<type>: <description>

[optional body]
```

#### type
- `feat`: 新機能
- `fix`: バグ修正
- `docs`: ドキュメントのみの変更
- `style`: コードフォーマット（機能影響なし）
- `refactor`: リファクタ（機能変更・バグ修正以外）
- `perf`: パフォーマンス改善
- `test`: テスト追加・修正
- `chore`: ビルド・補助ツール変更

#### 例
```
feat: CC-RX パーサの初期実装
fix: 64KB品でミラー元アドレスのゼロパディング誤り
docs: README に動作環境の最低バージョンを追記
refactor: Compilersモジュールに裸関数を集約
```

## コードオブコンダクト

技術的議論は歓迎しますが、参加者を尊重した建設的なコミュニケーションをお願いします。

## ライセンス

このプロジェクトは [MIT License](LICENSE) で公開されています。
Pull Request を送る = MIT License の下にコントリビュートすることに同意したものとみなします。
