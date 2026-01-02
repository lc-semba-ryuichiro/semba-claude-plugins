---
name: webpify
description: 画像ファイルを WebP 形式に変換
argument-hint: "<対象パス> [-q 品質] [-o 出力先] [-r] [-f] [--lossless]"
allowed-tools:
  - Bash
  - Glob
  - Grep
  - Read
---

# 画像 WebP 変換コマンド

image-optimizerサブエージェントを使用して、以下の画像変換タスクを実行してください。

**引数**: $ARGUMENTS

## コマンド実行

webpifyはnpxで実行する。

```bash
npx @semba-ryuichiro/webpify@latest [対象パス] [オプション]
```

## オプション

| オプション                | 説明                        |
| -------------------- | ------------------------- |
| `-q, --quality <n>`  | 品質レベル (1-100, デフォルト: 100) |
| `-o, --output <dir>` | 出力ディレクトリ                  |
| `-r, --recursive`    | サブディレクトリも再帰的に処理           |
| `-f, --force`        | 既存ファイルを上書き                |
| `--lossless`         | 可逆圧縮モードで変換                |
| `--quiet`            | 統計出力を抑制                   |

## 実行例

```bash
# 単一ファイル変換（品質 100）
npx @semba-ryuichiro/webpify@latest image.png

# ディレクトリ一括変換（品質 80）
npx @semba-ryuichiro/webpify@latest ./images -q 80

# 再帰的に変換
npx @semba-ryuichiro/webpify@latest ./assets -r -q 80

# 出力先を指定
npx @semba-ryuichiro/webpify@latest ./images -o ./webp-output

# lossless（可逆圧縮）モードで変換
npx @semba-ryuichiro/webpify@latest ./images --lossless
```

## 注意事項

- 対象パスが存在しない場合はエラーを報告する
- デフォルトでは既存のWebPファイルはスキップされる
- 上書きする場合は `-f` オプションを使用する
