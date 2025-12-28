# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Claude Code プラグインを管理するモノレポ。`plugins/` ディレクトリに各プラグインを配置し、`.claude-plugin/marketplace.json` でプラグイン一覧を管理する。

## Commands

```bash
# Linting
pnpm lint                    # 全リンター実行（biome, yaml, actions）
pnpm lint:biome              # JS/TS/JSON
pnpm lint:yaml               # yamllint（mise経由）
pnpm lint:actions            # actionlint, ghalint, zizmor（mise経由）
pnpm lint:remark             # Markdownリント
pnpm lint:textlint           # 日本語文章リント
pnpm lint:secretlint         # シークレット検出

# Formatting
pnpm format                  # フォーマット実行
pnpm format:check            # フォーマットチェックのみ
pnpm lint:fix                # biome自動修正
pnpm lint:remark:fix         # remark自動修正
pnpm lint:textlint:fix       # textlint自動修正
```

## Git Hooks (lefthook)

- **pre-commit**: biome format、remark、textlintを実行し自動修正
- **commit-msg**: conventional commit形式を強制（commitlint）
- **pre-push**: 全リンター並列実行

## Commit Convention

Conventional Commits形式を使用。許可されたtype:
`feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`

- subject: 最大72文字
- body: 行あたり最大100文字

## Architecture

```text
.
├── .claude-plugin/
│   └── marketplace.json     # プラグイン一覧（マーケットプレース定義）
├── plugins/
│   └── {plugin-name}/
│       ├── .claude-plugin/
│       │   └── plugin.json  # プラグインマニフェスト
│       ├── commands/        # スラッシュコマンド定義（.md）
│       ├── skills/          # スキル定義
│       │   └── {skill}/
│       │       ├── SKILL.md
│       │       └── references/
│       └── README.md
└── pnpm-workspace.yaml      # 依存カタログ（catalogMode: strict）
```

## Plugin Development

新規プラグイン作成時:

1. `plugins/{plugin-name}/` を作成
2. `.claude-plugin/plugin.json` にマニフェスト定義
3. `commands/` にコマンド、`skills/` にスキルを配置
4. ルートの `.claude-plugin/marketplace.json` にプラグインを登録

## Tool Requirements

一部ツールは mise 経由でインストールが必要:

- yamllint
- actionlint
- ghalint
- zizmor
