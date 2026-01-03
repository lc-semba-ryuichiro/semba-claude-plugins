---
name: atl-fetch-confluence
description: Confluence ページ情報を取得
argument-hint: "<Confluence URL> [-f format] [-d] [-o dir] [--diff]"
allowed-tools:
  - Bash
  - Read
---

# Confluence 情報取得コマンド

confluence-fetcherサブエージェントを使用して、Confluenceページ情報を取得してください。

**引数**: $ARGUMENTS

## コマンド実行

atl-fetchはnpxで実行する。

```bash
npx atl-fetch [Confluence URL] [オプション]
```

## オプション

| オプション              | 説明                             |
| ------------------ | ------------------------------ |
| `-f, --format`     | 出力形式 (json/markdown/yaml)      |
| `-d, --download`   | 添付ファイルをダウンロード                  |
| `-o, --dir <path>` | ダウンロード先ディレクトリ（`--download` 必須） |
| `--diff`           | 差分のみ表示                         |
| `-v, --verbose`    | 詳細出力を有効化                       |
| `--debug`          | デバッグ出力を有効化（開発者向け）              |

## 実行例

```bash
# ページ情報を取得（JSON）
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title

# Markdown 形式で取得
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title -f markdown

# 添付ファイルをダウンロード
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title -d -o ./downloads

# 差分のみ表示
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title --diff
```

## 事前確認

実行前に以下の環境変数が設定されているか確認する。

- `ATLASSIAN_EMAIL`
- `ATLASSIAN_API_TOKEN`

## 注意事項

- 対象のConfluenceスペースへのアクセス権が必要
- URLは `https://{org}.atlassian.net/wiki/spaces/{SPACE}/pages/{ID}/{TITLE}` 形式で指定
- 認証エラーが発生した場合は環境変数を確認する
