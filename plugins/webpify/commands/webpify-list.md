---
name: webpify-list
description: WebPファイルの一覧と情報を表示
argument-hint: "<対象ディレクトリ> [-r] [--absolute]"
allowed-tools:
  - Bash
  - Glob
---

# WebPファイル一覧コマンド

image-optimizerサブエージェントを使用して、WebPファイルの一覧を取得してください。

**引数**: $ARGUMENTS

## コマンド実行

```bash
npx @semba-ryuichiro/webpify@latest [対象ディレクトリ] --list [-r] [--absolute]
```

## オプション

| オプション             | 説明              |
| ----------------- | --------------- |
| `-r, --recursive` | サブディレクトリも再帰的に検索 |
| `--absolute`      | 絶対パスで表示         |

## 出力形式

```text
--- WebP File List ---
File                                     Size         Width    Height
----------------------------------------------------------------------
sample.webp                              104 B        100      100
```

## 実行例

```bash
# 現在のディレクトリのWebPファイル一覧
npx @semba-ryuichiro/webpify@latest . --list

# 指定ディレクトリのWebPファイル一覧
npx @semba-ryuichiro/webpify@latest ./images --list

# サブディレクトリも含めて再帰的に検索
npx @semba-ryuichiro/webpify@latest ./assets --list -r

# 絶対パスで表示
npx @semba-ryuichiro/webpify@latest ./images --list --absolute

# 再帰 + 絶対パス
npx @semba-ryuichiro/webpify@latest ./assets --list -r --absolute
```

## 注意事項

- 対象ディレクトリが存在しない場合はエラーを報告する
- WebPファイルが存在しない場合は空の結果を表示する
- `-r`オプションを指定するとサブディレクトリ内のWebPファイルも一覧表示する
