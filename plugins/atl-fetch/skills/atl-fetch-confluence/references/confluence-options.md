# Confluence オプション詳細ガイド

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
- [バージョン履歴について](#バージョン履歴について)
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
  "id": "12345678",
  "title": "ページタイトル",
  "spaceKey": "DEV",
  "body": "<p>ページ本文...</p>",
  "currentVersion": 5,
  "versions": [
    {
      "number": 5,
      "author": "user@example.com",
      "created": "2024-01-10T00:00:00.000Z",
      "message": "更新コメント"
    },
    {
      "number": 4,
      "author": "user@example.com",
      "created": "2024-01-05T00:00:00.000Z",
      "message": null
    }
  ],
  "attachments": [
    {
      "id": "67890",
      "filename": "diagram.png",
      "mimeType": "image/png",
      "size": 54321
    }
  ]
}
```

### Markdown (`-f markdown`)

人間が読みやすい形式。ドキュメント化に適している。Confluenceのフォーマットをできるだけ保持して変換される。

### YAML (`-f yaml`)

設定ファイル形式。構造化データとして扱いやすい。

## 添付ファイルのダウンロード

`-d` オプションと `-o` オプションを組み合わせて使用する。

```bash
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title -d -o ./attachments
```

ダウンロードされるファイルは元のファイル名で保存される。

## 差分表示（`--diff`）

バージョン間の変更点のみを表示する。

```bash
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title --diff
```

**出力例:**

```diff
--- v4 (2024-01-05)
+++ v5 (2024-01-10)
@@ -10,7 +10,7 @@
 <p>変更前のテキスト</p>
-<p>削除された行</p>
+<p>追加された行</p>
 <p>変更後のテキスト</p>
```

## バージョン履歴について

Confluenceページは編集ごとにバージョンが作成される。`versions[]` には履歴情報が含まれる。

- `number`: バージョン番号
- `author`: 更新者
- `created`: 更新日時
- `message`: 変更コメント（ある場合）

## パイプでの活用

他のコマンドと組み合わせて使用できる。

```bash
# jq でフィルタリング
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title | jq '.title'

# yq で YAML 処理
npx atl-fetch https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title -f yaml | yq '.versions'
```
