## 新規プラグイン追加

### プラグイン名

<!-- 例: diagram-drawio -->

### 概要

<!-- プラグインの目的・機能を簡潔に説明してください -->

### 提供する機能

<!-- 該当するものにチェックを入れてください -->

- [ ] commands（スラッシュコマンド）
- [ ] skills（スキル）
- [ ] agents（エージェント）
- [ ] hooks（フック）

### プラグイン構成

<!-- 主要なファイル・ディレクトリを記載してください -->

```text
plugins/{plugin-name}/
├── .claude-plugin/
│   └── plugin.json
├── commands/
├── skills/
└── README.md
```

### チェックリスト

- [ ] `plugins/{plugin-name}/.claude-plugin/plugin.json` を作成した
- [ ] `.claude-plugin/marketplace.json` にプラグインを登録した
- [ ] `README.md` を作成した
- [ ] `pnpm lint` が通ること
- [ ] PRタイトルが `feat(plugins): add {plugin-name} plugin` 形式であること
