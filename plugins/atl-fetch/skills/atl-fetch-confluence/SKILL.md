---
name: atl-fetch-confluence
description: atl-fetch CLI を使った Confluence 情報取得のガイドを提供するスキル。「Confluence ページを取得したい」「Confluence のドキュメントを見たい」「atl-fetch で Confluence を取得」「Confluence のバージョン履歴を確認」「Wiki ページの内容を取得」などのリクエストで使用する。
allowed-tools:
  - Bash
  - Read
---

# Confluence 情報取得ガイド

## 目次

- [概要](#概要)
- [事前準備チェックリスト](#事前準備チェックリスト)
- [実行方法](#実行方法)
- [CLI オプション一覧](#cli-オプション一覧)
  - [認証情報の確認](#認証情報の確認)
- [URL フォーマット](#url-フォーマット)
- [よくある使用パターン](#よくある使用パターン)
  - [ページ情報を JSON で取得](#ページ情報を-json-で取得)
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

atl-fetchはAtlassian CloudからConfluenceページ情報を取得するCLIツール。ページ本文、バージョン履歴、添付ファイルを一括で取得できる。

## 事前準備チェックリスト

取得する前に確認する。

- [ ] 環境変数 `ATLASSIAN_EMAIL` が設定されているか
- [ ] 環境変数 `ATLASSIAN_API_TOKEN` が設定されているか
- [ ] 対象のConfluenceスペースへのアクセス権があるか
- [ ] Node.jsがインストールされているか

## 実行方法

atl-fetchはnpxで都度実行する。グローバルインストールは不要。

```bash
npx atl-fetch [Confluence URL] [オプション]
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

ConfluenceページURLは以下の形式で指定する。

```text
https://{org}.atlassian.net/wiki/spaces/{SPACE}/pages/{ID}/{TITLE}
```

**例:**

- `https://mycompany.atlassian.net/wiki/spaces/DEV/pages/12345678/Getting+Started`
- `https://example.atlassian.net/wiki/spaces/DOCS/pages/98765432/API+Reference`

## よくある使用パターン

### ページ情報を JSON で取得

```bash
npx atl-fetch https://mycompany.atlassian.net/wiki/spaces/DEV/pages/12345678/Guide
```

### Markdown 形式で取得

```bash
npx atl-fetch https://mycompany.atlassian.net/wiki/spaces/DEV/pages/12345678/Guide -f markdown
```

### 添付ファイルをダウンロード

```bash
npx atl-fetch https://mycompany.atlassian.net/wiki/spaces/DEV/pages/12345678/Guide -d -o ./downloads
```

### 差分のみ表示

```bash
npx atl-fetch https://mycompany.atlassian.net/wiki/spaces/DEV/pages/12345678/Guide --diff
```

## 出力内容

Confluenceページから以下の情報を取得する。

| フィールド          | 説明       |
| -------------- | -------- |
| id             | ページ ID   |
| title          | ページタイトル  |
| spaceKey       | スペースキー   |
| body           | ページ本文    |
| currentVersion | 現在のバージョン |
| versions\[]    | バージョン履歴  |
| attachments\[] | 添付ファイル一覧 |

## 出力形式

### JSON 形式（デフォルト）

```json
{
  "id": "12345678",
  "title": "ページタイトル",
  "spaceKey": "DEV",
  "body": "ページ本文...",
  "currentVersion": 5,
  "versions": [],
  "attachments": []
}
```

### Markdown 形式

```markdown
# ページタイトル

**スペース**: DEV
**バージョン**: 5

## 本文

ページ本文...

## バージョン履歴

- v5 [2024-01-10] - 更新者名
- v4 [2024-01-05] - 更新者名
```

## トラブルシューティング

### 認証エラーが発生する

環境変数を確認する。

```bash
echo $ATLASSIAN_EMAIL
echo $ATLASSIAN_API_TOKEN
```

### 権限エラーが発生する

対象スペースへのアクセス権を確認する。

### URL が認識されない

URLフォーマットが正しいか確認する。`/wiki/spaces/` が含まれているか確認。

## 追加リソース

### リファレンスファイル

詳細なオプション説明については以下を参照。

- `references/confluence-options.md` ... オプションの詳細説明、環境変数設定ガイド
