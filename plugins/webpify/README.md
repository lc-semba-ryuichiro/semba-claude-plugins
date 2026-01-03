# webpify Plugin

PNG/JPEG/GIF画像をWebP形式に変換するためのClaude Codeプラグイン。

## 概要

[@semba-ryuichiro/webpify](https://github.com/semba-yui/webpify) CLIを活用して、画像ファイルを効率的にWebP形式に変換する。ファイルサイズを削減しながら画質を維持し、Webパフォーマンスを向上させる。

## 前提条件

- Node.js 22.0.0以上

## 機能

### スキル

- webpify … webpify CLIの使い方、品質設定ガイド、ベストプラクティスを提供

### コマンド

- /webpify … 画像ファイルをWebP形式に変換
- /webpify:list … WebPファイルの一覧と情報を表示

### エージェント

- image-optimizer … 画像の分析と最適化を自動実行

## 使用例

### 画像変換

```text
/webpify ./images -q 80
```

### WebP ファイル一覧

```text
/webpify:list ./images
```

### 画像最適化（エージェント）

```text
画像を最適化して
```

## 品質設定ガイド

| ユースケース         | 推奨品質   |
| -------------- | ------ |
| ポートフォリオ、製品画像   | 90-100 |
| 一般的な Web コンテンツ | 70-85  |
| サムネイル、背景、アイコン  | 50-70  |

## CLI オプション

| オプション                | 説明            |
| -------------------- | ------------- |
| `-q, --quality <n>`  | 品質レベル (1-100) |
| `-o, --output <dir>` | 出力ディレクトリ      |
| `-r, --recursive`    | 再帰処理          |
| `-f, --force`        | 上書き           |
| `--lossless`         | 可逆圧縮モードで変換    |
| `--list`             | 一覧表示          |
| `--absolute`         | 一覧表示時に絶対パスで表示 |
| `--quiet`            | 統計出力抑制        |

## ライセンス

MIT
