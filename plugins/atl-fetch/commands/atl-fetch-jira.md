---
name: atl-fetch-jira
description: Jira 課題情報を取得
argument-hint: "<Jira URL> [-f format] [-d] [-o dir] [--diff]"
allowed-tools:
  - Bash
  - Read
---

# Jira 情報取得コマンド

jira-fetcherサブエージェントを使用して、Jira課題情報を取得してください。

**引数**: $ARGUMENTS

## コマンド実行

atl-fetchはnpxで実行する。

```bash
npx atl-fetch [Jira URL] [オプション]
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
# 課題情報を取得（JSON）
npx atl-fetch https://example.atlassian.net/browse/PROJ-123

# Markdown 形式で取得
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 -f markdown

# 添付ファイルをダウンロード
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 -d -o ./downloads

# 差分のみ表示
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 --diff
```

## 事前確認

実行前に以下の環境変数が設定されているか確認する。

- `ATLASSIAN_EMAIL`
- `ATLASSIAN_API_TOKEN`

## 注意事項

- 対象のJiraプロジェクトへのアクセス権が必要
- URLは `https://{org}.atlassian.net/browse/{KEY}` 形式で指定
- 認証エラーが発生した場合は環境変数を確認する
