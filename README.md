# semba-claude-plugins

[![CodeQL](https://github.com/lc-semba-ryuichiro/semba-claude-plugins/actions/workflows/github-code-scanning/codeql/badge.svg)](https://github.com/lc-semba-ryuichiro/semba-claude-plugins/actions/workflows/github-code-scanning/codeql)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=lc-semba-ryuichiro_semba-claude-plugins\&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=lc-semba-ryuichiro_semba-claude-plugins)
![CodeRabbit Pull Request Reviews](https://img.shields.io/coderabbit/prs/github/lc-semba-ryuichiro/semba-claude-plugins?utm_source=oss\&utm_medium=github\&utm_campaign=lc-semba-ryuichiro%2Fsemba-claude-plugins\&labelColor=171717\&color=FF570A\&link=https%3A%2F%2Fcoderabbit.ai\&label=CodeRabbit+Reviews)
[![DeepWiki](https://img.shields.io/badge/DeepWiki-lc--semba--ryuichiro%2Fsemba--claude--plugins-blue.svg?logo=data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAyCAYAAAAnWDnqAAAAAXNSR0IArs4c6QAAA05JREFUaEPtmUtyEzEQhtWTQyQLHNak2AB7ZnyXZMEjXMGeK/AIi+QuHrMnbChYY7MIh8g01fJoopFb0uhhEqqcbWTp06/uv1saEDv4O3n3dV60RfP947Mm9/SQc0ICFQgzfc4CYZoTPAswgSJCCUJUnAAoRHOAUOcATwbmVLWdGoH//PB8mnKqScAhsD0kYP3j/Yt5LPQe2KvcXmGvRHcDnpxfL2zOYJ1mFwrryWTz0advv1Ut4CJgf5uhDuDj5eUcAUoahrdY/56ebRWeraTjMt/00Sh3UDtjgHtQNHwcRGOC98BJEAEymycmYcWwOprTgcB6VZ5JK5TAJ+fXGLBm3FDAmn6oPPjR4rKCAoJCal2eAiQp2x0vxTPB3ALO2CRkwmDy5WohzBDwSEFKRwPbknEggCPB/imwrycgxX2NzoMCHhPkDwqYMr9tRcP5qNrMZHkVnOjRMWwLCcr8ohBVb1OMjxLwGCvjTikrsBOiA6fNyCrm8V1rP93iVPpwaE+gO0SsWmPiXB+jikdf6SizrT5qKasx5j8ABbHpFTx+vFXp9EnYQmLx02h1QTTrl6eDqxLnGjporxl3NL3agEvXdT0WmEost648sQOYAeJS9Q7bfUVoMGnjo4AZdUMQku50McDcMWcBPvr0SzbTAFDfvJqwLzgxwATnCgnp4wDl6Aa+Ax283gghmj+vj7feE2KBBRMW3FzOpLOADl0Isb5587h/U4gGvkt5v60Z1VLG8BhYjbzRwyQZemwAd6cCR5/XFWLYZRIMpX39AR0tjaGGiGzLVyhse5C9RKC6ai42ppWPKiBagOvaYk8lO7DajerabOZP46Lby5wKjw1HCRx7p9sVMOWGzb/vA1hwiWc6jm3MvQDTogQkiqIhJV0nBQBTU+3okKCFDy9WwferkHjtxib7t3xIUQtHxnIwtx4mpg26/HfwVNVDb4oI9RHmx5WGelRVlrtiw43zboCLaxv46AZeB3IlTkwouebTr1y2NjSpHz68WNFjHvupy3q8TFn3Hos2IAk4Ju5dCo8B3wP7VPr/FGaKiG+T+v+TQqIrOqMTL1VdWV1DdmcbO8KXBz6esmYWYKPwDL5b5FA1a0hwapHiom0r/cKaoqr+27/XcrS5UwSMbQAAAABJRU5ErkJggg==)](https://deepwiki.com/lc-semba-ryuichiro/semba-claude-plugins)
[![Lint](https://github.com/lc-semba-ryuichiro/semba-claude-plugins/actions/workflows/lint.yml/badge.svg)](https://github.com/lc-semba-ryuichiro/semba-claude-plugins/actions/workflows/lint.yml)

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
