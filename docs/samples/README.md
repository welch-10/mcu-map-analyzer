# Sample Map Files

ツールの動作確認・スクリーンショット・テスト用の匿名化済み map ファイル。

## sample_ccrl.map

CC-RL (RL78) の典型的な mapファイルのサンプル。以下の手順で匿名化済み:

| 元 | 置換後 |
|-----|--------|
| プロジェクトコード | `SAMPLE_PROJ_001` |
| `*.obj` ファイル名 (65個) | `module_001.obj` 〜 `module_065.obj` |
| カスタムセクション名 (57個) | `seg_01` 〜 `seg_57` |
| C シンボル名 (約11,700個) | `_sym_00001` 〜 `_sym_11734` |

### スペック

- ファイルサイズ: 約 2.1 MB / 45,625 行
- コンパイラ: CC-RL (Renesas Optimizing Linker V3.07)
- 対象デバイス: RL78/G23 384KB品 (Renesas 公開型番)
- ROM 使用率: 約 93%
- ファイル数: 78
- セクション数: 15
- ミラー領域: 19.75 KB

### 使い方

1. このファイルをダウンロード
2. [MCU Map Analyzer](https://welch-10.github.io/mcu-map-analyzer/) を開く
3. ファイルを投入

または、ツールの welcome 画面の「サンプルファイルを解析」ボタンから直接読み込めます。

## ライセンス

サンプルファイルは MIT License (本リポジトリと同じ) で配布されます。
