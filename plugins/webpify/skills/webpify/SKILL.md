---
name: webpify
description: webpify CLI の使い方、WebP 変換のベストプラクティス、品質設定ガイドを提供するスキル。「webpify の使い方」「画像を WebP に変換したい」「WebP 変換のベストプラクティス」「画像最適化の品質設定」「webpify のオプション」などのリクエストで使用する。
allowed-tools:
  - Bash
  - Glob
  - Grep
  - Read
---

# webpify 使用ガイド

## 概要

webpifyはPNG/JPEG/GIF画像をWebP形式に変換するCLIツール。ファイルサイズを削減しながら画質を維持し、Webパフォーマンスを向上させる。

## 事前準備チェックリスト

変換する前に確認する。

- [ ] Node.js 22.0.0以上がインストールされているか
- [ ] 対象画像ファイルのバックアップは不要か
- [ ] 出力先ディレクトリの書き込み権限があるか

***

## 実行方法

webpifyはnpxで都度実行する。グローバルインストールは不要。

```bash
npx @semba-ryuichiro/webpify@latest [入力パス] [オプション]
```

***

## CLI オプション一覧

| オプション                | 説明                | デフォルト      |
| -------------------- | ----------------- | ---------- |
| `-o, --output <dir>` | 出力ディレクトリを指定       | 元ファイルと同じ場所 |
| `-q, --quality <n>`  | 品質レベル (1-100)     | 100        |
| `-r, --recursive`    | サブディレクトリも再帰的に処理   | false      |
| `-f, --force`        | 既存の WebP ファイルを上書き | false      |
| `--lossless`         | 可逆圧縮モードで変換        | false      |
| `--list`             | WebP ファイルの情報を一覧表示 | -          |
| `--absolute`         | 一覧表示時に絶対パスで表示     | false      |
| `--quiet`            | 統計情報の出力を抑制        | false      |
| `-v, --version`      | バージョン表示           | -          |
| `-h, --help`         | ヘルプ表示             | -          |

***

## よくある使用パターン

### 単一ファイル変換

```bash
npx @semba-ryuichiro/webpify@latest image.png
```

### ディレクトリ一括変換

```bash
npx @semba-ryuichiro/webpify@latest ./images
```

### 品質を指定して変換

```bash
npx @semba-ryuichiro/webpify@latest ./images -q 80
```

### 再帰的に変換（サブディレクトリ含む）

```bash
npx @semba-ryuichiro/webpify@latest ./assets -r
```

### 出力先を別ディレクトリに指定

```bash
npx @semba-ryuichiro/webpify@latest ./images -o ./webp-output
```

### 既存ファイルを上書きして再変換

```bash
npx @semba-ryuichiro/webpify@latest ./images -q 75 -f
```

### lossless（可逆圧縮）モードで変換

```bash
npx @semba-ryuichiro/webpify@latest ./images --lossless
```

### WebP ファイル一覧を確認

```bash
npx @semba-ryuichiro/webpify@latest ./images --list
```

### WebP ファイル一覧を絶対パスで表示

```bash
npx @semba-ryuichiro/webpify@latest ./images --list --absolute
```

### CI/CD 向け（サイレント実行）

```bash
npx @semba-ryuichiro/webpify@latest ./assets -r -q 80 -f --quiet
```

***

## 品質設定ガイドライン

品質設定はユースケースに応じて選択する。詳細は `references/quality-guide.md` を参照。

ただし、デフォルトはあくまで100として、この -qオプションを指定する必要はない。ユーザーからユースケースの明示的な指定があった場合のみ、AskUserQuestionを利用し、どの品質を利用するかユーザーに確認する。

| ユースケース         | 推奨品質       | 説明          |
| -------------- | ---------- | ----------- |
| ポートフォリオ、製品画像   | 90-100     | 視覚的品質を最優先   |
| 一般的な Web コンテンツ | 70-85      | サイズと品質のバランス |
| サムネイル、背景、アイコン  | 50-70      | ファイルサイズを最優先 |
| アーカイブ、原本保存     | --lossless | 品質劣化なし      |

losslessモードは元の画像データを完全保持する。ファイルサイズは元より大きくなる場合がある。

***

## 出力形式

### 単一ファイル変換時

```
Converted: image.png (1.2MB -> 320KB, 73.3%)
```

### ディレクトリ変換時

```
[1/10] Processing: image1.png
[2/10] Processing: image2.jpg
...
Summary:
  Total files: 10
  Converted: 8
  Skipped: 2
  Errors: 0
  Size reduction: 68.5%
```

### --list 実行時

```text
--- WebP File List ---
File                                     Size         Width    Height
----------------------------------------------------------------------
image_00.webp                            166.68 KB    900      540
image_01.webp                            118.35 KB    900      540
image_02.webp                            41.54 KB     900      540
image_03.webp                            62.07 KB     900      540
image_04.webp                            97.07 KB     900      540
image_05.webp                            46.01 KB     900      540
```

***

## 終了コード

| コード | 意味                           |
| --- | ---------------------------- |
| 0   | 正常終了                         |
| 1   | エラー発生（ファイル不存在、無効な品質値、処理失敗など） |

***

## トラブルシューティング

### 変換後もファイルサイズが大きい

品質を下げるか、元画像が既に最適化されている可能性がある。

```bash
# 品質を下げて再変換
npx @semba-ryuichiro/webpify@latest image.png -q 75 -f
```

### 既存の WebP がスキップされる

`-f` オプションで上書きを有効にする。

```bash
npx @semba-ryuichiro/webpify@latest ./images -f
```

### サブディレクトリの画像が変換されない

`-r` オプションで再帰処理を有効にする。

```bash
npx @semba-ryuichiro/webpify@latest ./assets -r
```

***

## 追加リソース

### リファレンスファイル

詳細なガイドラインについては以下を参照。

- `references/quality-guide.md` … 品質設定の詳細ガイド、ユースケース別の推奨設定。
