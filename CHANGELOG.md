# Changelog

このプロジェクトのすべての注目すべき変更は、このファイルに記録されます。

形式は [Keep a Changelog](https://keepachangelog.com/ja/1.1.0/) に基づいており、
このプロジェクトは [セマンティックバージョニング](https://semver.org/lang/ja/) を遵守しています。

## 目次

- [Unreleased](#unreleased)
- [1.0.0 - 2025-12-29](#100---2025-12-29)
  - [Added](#added)

## [Unreleased][]

## [1.0.0][] - 2025-12-29

### Added

#### プラグイン

- diagram-drawio: draw\.io（diagrams.net）のXML形式で図を生成するプラグイン
  - フローチャート、シーケンス図、アーキテクチャ図、ER図、AWSアーキテクチャ図に対応
  - `/diagram-drawio` スラッシュコマンド
  - スキルによる自動起動対応
  - 日本語フォント対応（Hiragino Sans / Yu Gothic / Noto Sans JP）
  - PNG出力時も正しく表示される高品質な図の生成
  - AWSアイコンリファレンス、デザイン原則、XMLテンプレート付属

#### 開発環境

- Biome 2.xによるJS/TS/JSONのリント・フォーマット
- RemarkによるMarkdownリント
- textlintによる日本語文章リント
- secretlintによるシークレット検出
- LefthookによるGit Hooks
  - pre-commit: 自動フォーマット・リント
  - commit-msg: Conventional Commits形式チェック
  - pre-push: 全リンター並列実行
- commitlintによるConventional Commits形式の強制

#### プロジェクト基盤

- プラグインマーケットプレース基盤（`.claude-plugin/marketplace.json`）
- pnpmワークスペース構成（catalogMode: strict）

#### ドキュメント

- README.md: プロジェクト概要とインストール方法
- CONTRIBUTING.md: コントリビューションガイド
- SECURITY.md: セキュリティポリシー
- CODE\_OF\_CONDUCT.md: 行動規範
- CLAUDE.md: Claude Code開発ガイド

[Unreleased]: https://github.com/lc-semba-ryuichiro/semba-claude-plugins/compare/v1.0.0...HEAD

[1.0.0]: https://github.com/lc-semba-ryuichiro/semba-claude-plugins/releases/tag/v1.0.0
