# Jira オプション詳細ガイド

## 目次

- [環境変数の設定](#環境変数の設定)
  - [ATLASSIAN\_EMAIL](#atlassian_email)
  - [ATLASSIAN\_API\_TOKEN](#atlassian_api_token)
  - [.env ファイルでの設定](#env-ファイルでの設定)
  - [認証情報の確認](#認証情報の確認)
- [出力形式の詳細](#出力形式の詳細)
  - [JSON (`-f json`)](#json--f-json)
  - [Markdown (`-f markdown`)](#markdown--f-markdown)
  - [YAML (`-f yaml`)](#yaml--f-yaml)
- [添付ファイルのダウンロード](#添付ファイルのダウンロード)
- [差分表示（`--diff`）](#差分表示--diff)
- [パイプでの活用](#パイプでの活用)

## 環境変数の設定

### ATLASSIAN\_EMAIL

Atlassianアカウントのメールアドレス。

```bash
export ATLASSIAN_EMAIL="your-email@example.com"
```

### ATLASSIAN\_API\_TOKEN

Atlassian APIトークン。以下から取得する。
<https://id.atlassian.com/manage-profile/security/api-tokens>

```bash
export ATLASSIAN_API_TOKEN="your-api-token"
```

### .env ファイルでの設定

プロジェクトルートに `.env` ファイルを作成して設定することも可能。

```text
ATLASSIAN_EMAIL=your-email@example.com
ATLASSIAN_API_TOKEN=your-api-token
```

### 認証情報の確認

`atl-fetch auth check` で認証情報が正しく設定されているか確認できる。

```bash
npx atl-fetch auth check
```

出力例（設定済み）:

```text
認証情報チェック
────────────────────────────────────────
✓ 認証情報が正しく設定されています
  設定状態:
    ATLASSIAN_EMAIL:     user@example.com
    ATLASSIAN_API_TOKEN: ***abcd
```

## 出力形式の詳細

### JSON (`-f json`)

機械可読な形式。プログラムでの処理に適している。

**出力例:**

```json
{
  "key": "PROJ-123",
  "summary": "課題タイトル",
  "description": "課題の詳細説明",
  "comments": [
    {
      "id": "12345",
      "author": "user@example.com",
      "body": "コメント内容",
      "created": "2024-01-01T00:00:00.000Z",
      "updated": "2024-01-01T00:00:00.000Z"
    }
  ],
  "changelog": [
    {
      "field": "status",
      "from": "Open",
      "to": "In Progress",
      "author": "user@example.com",
      "created": "2024-01-01T00:00:00.000Z"
    }
  ],
  "attachments": [
    {
      "id": "67890",
      "filename": "screenshot.png",
      "mimeType": "image/png",
      "size": 12345
    }
  ]
}
```

### Markdown (`-f markdown`)

人間が読みやすい形式。ドキュメント化に適している。

### YAML (`-f yaml`)

設定ファイル形式。構造化データとして扱いやすい。

## 添付ファイルのダウンロード

`-d` オプションと `-o` オプションを組み合わせて使用する。

```bash
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 -d -o ./attachments
```

ダウンロードされるファイルは元のファイル名で保存される。

## 差分表示（`--diff`）

変更履歴のみを表示する。

```bash
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 --diff
```

**出力例:**

```text
[2024-01-01] status: Open → In Progress (user@example.com)
[2024-01-02] assignee: null → John Doe (user@example.com)
```

## パイプでの活用

他のコマンドと組み合わせて使用できる。

```bash
# jq でフィルタリング
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 | jq '.comments[].body'

# yq で YAML 処理
npx atl-fetch https://example.atlassian.net/browse/PROJ-123 -f yaml | yq '.summary'
```
