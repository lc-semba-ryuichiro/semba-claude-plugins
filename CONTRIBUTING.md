# コントリビューションガイド

このプロジェクトへの貢献に興味を持っていただきありがとうございます。

## 目次

- [開発環境のセットアップ](#開発環境のセットアップ)
  - [必須ツール](#必須ツール)
  - [セットアップ手順](#セットアップ手順)
- [開発コマンド](#開発コマンド)
- [Git Hooks](#git-hooks)
- [コミット規約](#コミット規約)
  - [フォーマット](#フォーマット)
  - [許可された type](#許可された-type)
  - [制限事項](#制限事項)
  - [コミット例](#コミット例)
- [プラグイン開発](#プラグイン開発)
  - [新規プラグインの作成](#新規プラグインの作成)
  - [ディレクトリ構造](#ディレクトリ構造)
  - [plugin.json の例](#pluginjson-の例)
- [プルリクエスト](#プルリクエスト)
  - [作成手順](#作成手順)
  - [PR チェックリスト](#pr-チェックリスト)
- [質問・相談](#質問相談)

## 開発環境のセットアップ

### 必須ツール

- Node.js（LTS推奨）
- [pnpm](https://pnpm.io/) v10.26.2以上
- [mise](https://mise.jdx.dev/)（リンターのインストールに必要）

### セットアップ手順

```bash
# リポジトリをクローン
git clone https://github.com/lc-semba-ryuichiro/semba-claude-plugins.git
cd semba-claude-plugins

# 依存関係をインストール
pnpm install

# mise でツールをインストール
mise install
```

## 開発コマンド

```bash
# フォーマット
pnpm format              # 自動修正
pnpm format:check        # チェックのみ

# リント
pnpm lint                # 全リンター実行
pnpm lint:biome          # JS/TS/JSON
pnpm lint:yaml           # YAML ファイル
pnpm lint:actions        # GitHub Actions
pnpm lint:remark         # Markdown
pnpm lint:textlint       # 日本語文章
pnpm lint:secretlint     # シークレット検出

# 自動修正
pnpm lint:fix            # Biome
pnpm lint:remark:fix     # Remark
pnpm lint:textlint:fix   # textlint
```

## Git Hooks

[Lefthook](https://github.com/evilmartians/lefthook) により以下の自動チェックが実行されます。

| フック        | 実行内容                                  |
| ---------- | ------------------------------------- |
| pre-commit | Biome フォーマット、Remark、textlint を実行し自動修正 |
| commit-msg | Conventional Commits 形式をチェック          |
| pre-push   | 全リンターを並列実行                            |

## コミット規約

[Conventional Commits](https://www.conventionalcommits.org/) 形式を採用しています。

### フォーマット

```text
<type>(<scope>): <subject>

<body>
```

### 許可された type

| type       | 用途                          |
| ---------- | --------------------------- |
| `feat`     | 新機能                         |
| `fix`      | バグ修正                        |
| `docs`     | ドキュメントのみの変更                 |
| `style`    | コードの意味に影響しない変更（空白、フォーマットなど） |
| `refactor` | バグ修正でも機能追加でもないコード変更         |
| `perf`     | パフォーマンス改善                   |
| `test`     | テストの追加・修正                   |
| `build`    | ビルドシステムや外部依存関係の変更           |
| `ci`       | CI 設定の変更                    |
| `chore`    | その他の変更                      |
| `revert`   | コミットの取り消し                   |

### 制限事項

- subject: 最大72文字
- body: 1行あたり最大100文字

### コミット例

```bash
feat(diagram-drawio): フローチャート作成機能を追加

- 基本図形の描画をサポート
- 接続線の自動配置機能を実装
```

## プラグイン開発

### 新規プラグインの作成

1. `plugins/{plugin-name}/` ディレクトリを作成
2. `.claude-plugin/plugin.json` にマニフェストを定義
3. コマンドを追加する場合は `commands/`、スキルを追加する場合は `skills/` に配置
4. `README.md` を作成
5. ルートの `.claude-plugin/marketplace.json` にプラグインを登録

### ディレクトリ構造

```text
plugins/{plugin-name}/
├── .claude-plugin/
│   └── plugin.json      # マニフェスト（必須）
├── commands/            # スラッシュコマンド（.md ファイル）
├── skills/              # スキル定義
│   └── {skill-name}/
│       ├── SKILL.md
│       └── references/
└── README.md            # プラグインの説明
```

### plugin.json の例

```json
{
  "name": "my-plugin",
  "version": "1.0.0",
  "description": "プラグインの説明"
}
```

## プルリクエスト

### 作成手順

1. フィーチャーブランチを作成: `git checkout -b feature/my-feature`
2. 変更をコミット（Conventional Commits形式で）
3. プッシュ: `git push origin feature/my-feature`
4. GitHubでプルリクエストを作成

### PR チェックリスト

- [ ] 全リンターが通過している（`pnpm lint`）
- [ ] フォーマットが適用されている（`pnpm format`）
- [ ] コミットメッセージがConventional Commits形式である
- [ ] 新機能や変更にドキュメント更新が伴う場合は更新している

## 質問・相談

不明点がある場合は、[GitHub Issues](https://github.com/lc-semba-ryuichiro/semba-claude-plugins/issues) で質問してください。
