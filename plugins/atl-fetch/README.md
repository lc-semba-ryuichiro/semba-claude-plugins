# atl-fetch Plugin

Atlassian Cloud (Jira / Confluence) の情報を取得するためのClaude Codeプラグイン。

## 概要

[atl-fetch](https://www.npmjs.com/package/atl-fetch) CLIを活用して、Jira課題やConfluenceページの情報を効率的に取得する。コメント、変更履歴、添付ファイルも一括で取得可能。

## 目次

- [前提条件](#前提条件)
  - [API トークンの取得](#api-トークンの取得)
- [機能](#機能)
  - [スキル](#スキル)
  - [コマンド](#コマンド)
  - [エージェント](#エージェント)
- [使用例](#使用例)
  - [Jira 課題の取得](#jira-課題の取得)
  - [Confluence ページの取得](#confluence-ページの取得)
  - [プロアクティブ取得（エージェント）](#プロアクティブ取得エージェント)
  - [複数リソースの一括取得](#複数リソースの一括取得)
  - [Markdown 形式での取得](#markdown-形式での取得)
  - [添付ファイルのダウンロード](#添付ファイルのダウンロード)
- [CLI オプション](#cli-オプション)
- [サブコマンド](#サブコマンド)
  - [`atl-fetch auth check`](#atl-fetch-auth-check)
- [URL フォーマット](#url-フォーマット)
  - [Jira](#jira)
  - [Confluence](#confluence)
- [プラグイン構成](#プラグイン構成)
- [トラブルシューティング](#トラブルシューティング)
- [ライセンス](#ライセンス)

## 前提条件

- Node.js (npxが使用可能であること)
- Atlassian Cloudへのアクセス権
- 以下の環境変数の設定:
  - `ATLASSIAN_EMAIL`: Atlassianアカウントのメールアドレス
  - `ATLASSIAN_API_TOKEN`: Atlassian APIトークン

### API トークンの取得

1. <https://id.atlassian.com/manage-profile/security/api-tokens> にアクセス
2. 「APIトークンを作成」をクリック
3. トークン名を入力して作成
4. 表示されたトークンをコピーして環境変数に設定

```bash
export ATLASSIAN_EMAIL="your-email@example.com"
export ATLASSIAN_API_TOKEN="your-api-token"
```

## 機能

### スキル

| 名前                   | 説明                              |
| -------------------- | ------------------------------- |
| atl-fetch-jira       | Jira 情報取得のガイド、CLI オプション説明       |
| atl-fetch-confluence | Confluence 情報取得のガイド、CLI オプション説明 |

### コマンド

| 名前                    | 説明                  |
| --------------------- | ------------------- |
| /atl-fetch-jira       | Jira 課題情報を取得        |
| /atl-fetch-confluence | Confluence ページ情報を取得 |

### エージェント

| 名前                 | 説明                                  |
| ------------------ | ----------------------------------- |
| jira-fetcher       | Jira 情報取得支援（プロアクティブ + リアクティブ）       |
| confluence-fetcher | Confluence 情報取得支援（プロアクティブ + リアクティブ） |

## 使用例

### Jira 課題の取得

```text
/atl-fetch-jira https://example.atlassian.net/browse/PROJ-123
```

### Confluence ページの取得

```text
/atl-fetch-confluence https://example.atlassian.net/wiki/spaces/DEV/pages/123/Title
```

### プロアクティブ取得（エージェント）

会話中にJira/Confluence URLを言及するだけで、エージェントが自動的に情報取得を提案。

```text
この課題を確認して: https://example.atlassian.net/browse/PROJ-123
```

### 複数リソースの一括取得

```text
これらの課題をまとめて取得して:
- https://example.atlassian.net/browse/PROJ-1
- https://example.atlassian.net/browse/PROJ-2
```

### Markdown 形式での取得

```text
/atl-fetch-jira https://example.atlassian.net/browse/PROJ-123 -f markdown
```

### 添付ファイルのダウンロード

```text
/atl-fetch-jira https://example.atlassian.net/browse/PROJ-123 -d -o ./downloads
```

## CLI オプション

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

## サブコマンド

### `atl-fetch auth check`

認証情報の設定状態を確認する。

```bash
npx atl-fetch auth check
```

## URL フォーマット

### Jira

```text
https://{org}.atlassian.net/browse/{KEY}
```

**例:** `https://mycompany.atlassian.net/browse/PROJ-123`

### Confluence

```text
https://{org}.atlassian.net/wiki/spaces/{SPACE}/pages/{ID}/{TITLE}
```

**例:** `https://mycompany.atlassian.net/wiki/spaces/DEV/pages/12345678/Getting+Started`

## プラグイン構成

```text
plugins/atl-fetch/
├── .claude-plugin/
│   └── plugin.json
├── commands/
│   ├── atl-fetch-jira.md
│   └── atl-fetch-confluence.md
├── skills/
│   ├── atl-fetch-jira/
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── jira-options.md
│   └── atl-fetch-confluence/
│       ├── SKILL.md
│       └── references/
│           └── confluence-options.md
├── agents/
│   ├── jira-fetcher.md
│   └── confluence-fetcher.md
└── README.md
```

## トラブルシューティング

| 問題          | 解決策                                                |
| ----------- | -------------------------------------------------- |
| 認証エラー       | 環境変数 `ATLASSIAN_EMAIL` と `ATLASSIAN_API_TOKEN` を確認 |
| 権限エラー       | 対象プロジェクト/スペースへのアクセス権を確認                            |
| URL が認識されない | URL フォーマットが正しいか確認                                  |
| npx が見つからない | Node.js がインストールされているか確認                            |

## ライセンス

MIT
