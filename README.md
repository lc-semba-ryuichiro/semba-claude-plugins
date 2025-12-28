# semba-claude-plugins

Claude Codeプラグインを管理するリポジトリ。

## 目次

- [概要](#概要)
- [利用可能なプラグイン](#利用可能なプラグイン)
- [インストール](#インストール)
  - [前提条件](#前提条件)
  - [プラグインの追加](#プラグインの追加)
- [ディレクトリ構造](#ディレクトリ構造)
- [開発に参加する](#開発に参加する)
- [セキュリティ](#セキュリティ)
- [行動規範](#行動規範)
- [ライセンス](#ライセンス)
- [作者](#作者)

## 概要

このリポジトリは、[Claude Code](https://claude.ai/code) で使用できるカスタムプラグインを集約・管理します。
各プラグインは `plugins/` ディレクトリに配置され、`.claude-plugin/marketplace.json` で一覧管理されています。

## 利用可能なプラグイン

| プラグイン名                                     | 説明                         |
| ------------------------------------------ | -------------------------- |
| [diagram-drawio](./plugins/diagram-drawio) | draw\.io の XML 形式で高品質な図を作成 |

## インストール

### 前提条件

- [Claude Code CLI](https://claude.ai/code) がインストールされていること

### プラグインの追加

Claude Codeで以下のコマンドを実行してください。

```bash
/install-plugin https://github.com/lc-semba-ryuichiro/semba-claude-plugins
```

個別のプラグインを追加する場合は、以下のコマンドを実行します。

```bash
/install-plugin https://github.com/lc-semba-ryuichiro/semba-claude-plugins/plugins/diagram-drawio
```

## ディレクトリ構造

```text
.
├── .claude-plugin/
│   └── marketplace.json     # プラグイン一覧
├── plugins/
│   └── {plugin-name}/
│       ├── .claude-plugin/
│       │   └── plugin.json  # プラグインマニフェスト
│       ├── commands/        # スラッシュコマンド定義
│       ├── skills/          # スキル定義
│       └── README.md
└── pnpm-workspace.yaml
```

## 開発に参加する

プロジェクトへの貢献方法は [CONTRIBUTING.md](./CONTRIBUTING.md) を参照してください。

## セキュリティ

セキュリティに関する問題の報告方法は [SECURITY.md](./SECURITY.md) を参照してください。

## 行動規範

このプロジェクトは [CODE\_OF\_CONDUCT.md](./CODE_OF_CONDUCT.md) に定められた行動規範を採用しています。

## ライセンス

[MIT License](./LICENSE)

## 作者

Ryuichiro Semba
