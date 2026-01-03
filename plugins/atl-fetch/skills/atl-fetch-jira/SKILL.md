---
name: atl-fetch-jira
description: atl-fetch CLI を使った Jira 情報取得のガイドを提供するスキル。「Jira の課題を取得したい」「Jira チケットの情報を見たい」「atl-fetch で Jira を取得」「Jira 課題のコメントを確認」「Jira の変更履歴を見たい」などのリクエストで使用する。
allowed-tools:
  - Bash
  - Read
---

# Jira 情報取得ガイド

## 目次

- [概要](#概要)
- [事前準備チェックリスト](#事前準備チェックリスト)
- [実行方法](#実行方法)
- [CLI オプション一覧](#cli-オプション一覧)
  - [認証情報の確認](#認証情報の確認)
- [URL フォーマット](#url-フォーマット)
- [よくある使用パターン](#よくある使用パターン)
  - [課題情報を JSON で取得](#課題情報を-json-で取得)
  - [Markdown 形式で取得](#markdown-形式で取得)
  - [添付ファイルをダウンロード](#添付ファイルをダウンロード)
  - [差分のみ表示](#差分のみ表示)
- [出力内容](#出力内容)
- [出力形式](#出力形式)
  - [JSON 形式（デフォルト）](#json-形式デフォルト)
  - [Markdown 形式](#markdown-形式)
- [トラブルシューティング](#トラブルシューティング)
  - [認証エラーが発生する](#認証エラーが発生する)
  - [権限エラーが発生する](#権限エラーが発生する)
  - [URL が認識されない](#url-が認識されない)
- [追加リソース](#追加リソース)
  - [リファレンスファイル](#リファレンスファイル)

## 概要

atl-fetchはAtlassian CloudからJira課題情報を取得するCLIツール。課題の詳細、コメント、変更履歴、添付ファイルを一括で取得できる。

## 事前準備チェックリスト

取得する前に確認する。

- [ ] 環境変数 `ATLASSIAN_EMAIL` が設定されているか
- [ ] 環境変数 `ATLASSIAN_API_TOKEN` が設定されているか
- [ ] 対象のJiraプロジェクトへのアクセス権があるか
- [ ] Node.jsがインストールされているか

## 実行方法

atl-fetchはnpxで都度実行する。グローバルインストールは不要。

```bash
npx atl-fetch [Jira URL] [オプション]
```

## CLI オプション一覧

| オプション              | 説明                             | デフォルト |
| ------------------ | ------------------------------ | ----- |
| `-f, --format`     | 出力形式 (json/markdown/yaml)      | json  |
| `-d, --download`   | 添付ファイルをダウンロード                  | false |
| `-o, --dir <path>` | ダウンロード先ディレクトリ（`--download` 必須） | -     |
| `--diff`           | 差分のみ表示                         | false |
| `--color`          | カラー出力有効                        | true  |
| `--no-color`       | カラー出力無効                        | false |
| `-v, --verbose`    | 詳細出力を有効化                       | false |
| `--debug`          | デバッグ出力を有効化（開発者向け）              | false |

### 認証情報の確認

認証情報が正しく設定されているか確認する。

```bash
npx atl-fetch auth check
```

## URL フォーマット

Jira課題URLは以下の形式で指定する。

```text
https://{org}.atlassian.net/browse/{KEY}
```

**例:**

- `https://mycompany.atlassian.net/browse/PROJ-123`
- `https://example.atlassian.net/browse/DEV-456`

## よくある使用パターン

### 課題情報を JSON で取得

```bash
npx atl-fetch https://mycompany.atlassian.net/browse/PROJ-123
```

### Markdown 形式で取得

```bash
npx atl-fetch https://mycompany.atlassian.net/browse/PROJ-123 -f markdown
```

### 添付ファイルをダウンロード

```bash
npx atl-fetch https://mycompany.atlassian.net/browse/PROJ-123 -d -o ./downloads
```

### 差分のみ表示

```bash
npx atl-fetch https://mycompany.atlassian.net/browse/PROJ-123 --diff
```

## 出力内容

Jira課題から以下の情報を取得する。

| フィールド          | 説明                |
| -------------- | ----------------- |
| key            | 課題キー（例: PROJ-123） |
| summary        | 課題タイトル            |
| description    | 課題の説明             |
| comments\[]    | コメント一覧            |
| changelog\[]   | 変更履歴              |
| attachments\[] | 添付ファイル一覧          |

## 出力形式

### JSON 形式（デフォルト）

```json
{
  "key": "PROJ-123",
  "summary": "課題タイトル",
  "description": "課題の詳細説明...",
  "comments": [],
  "changelog": [],
  "attachments": []
}
```

### Markdown 形式

```markdown
# PROJ-123: 課題タイトル

## 説明

課題の詳細説明...

## コメント

- [2024-01-01] ユーザー名: コメント内容...

## 変更履歴

- [2024-01-01] ステータス: Open → In Progress
```

## トラブルシューティング

### 認証エラーが発生する

環境変数を確認する。

```bash
echo $ATLASSIAN_EMAIL
echo $ATLASSIAN_API_TOKEN
```

### 権限エラーが発生する

対象プロジェクトへのアクセス権を確認する。

### URL が認識されない

URLフォーマットが正しいか確認する。`/browse/` が含まれているか確認。

## 追加リソース

### リファレンスファイル

詳細なオプション説明については以下を参照。

- `references/jira-options.md` ... オプションの詳細説明、環境変数設定ガイド
