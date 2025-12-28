# diagram-drawio プラグイン

draw\.io（diagrams.net）のXML形式で高品質な図を作成するClaude Codeプラグイン。

## 目次

- [機能](#機能)
- [インストール](#インストール)
  - [方法1: マーケットプレースからインストール（推奨）](#方法1-マーケットプレースからインストール推奨)
  - [方法2: インタラクティブUIでインストール](#方法2-インタラクティブuiでインストール)
  - [方法3: チーム設定で自動化](#方法3-チーム設定で自動化)
- [使い方](#使い方)
  - [コマンド: `/diagram-drawio`](#コマンド-diagram-drawio)
  - [スキル自動起動](#スキル自動起動)
- [出力例](#出力例)
  - [ファイル保存](#ファイル保存)
  - [PNG変換（オプション）](#png変換オプション)
- [プラグイン構造](#プラグイン構造)
- [対応図の種類](#対応図の種類)
- [日本語フォント対応](#日本語フォント対応)
- [トラブルシューティング](#トラブルシューティング)
- [ライセンス](#ライセンス)
- [作成者](#作成者)

## 機能

- 複数種類の図に対応: フローチャート、シーケンス図、アーキテクチャ図、ER図
- 日本語フォント対応: PNG出力でも正しく表示される設定済み
- XMLテンプレート付き: すぐに使える完全なテンプレートを提供
- .drawioファイル出力: draw\.ioで直接編集可能

## インストール

### 方法1: マーケットプレースからインストール（推奨）

```shell
# マーケットプレースを追加
/plugin marketplace add lc-semba-ryuichiro/semba-claude-plugins

# プラグインをインストール
/plugin install diagram-drawio@semba-claude-plugins
```

### 方法2: インタラクティブUIでインストール

```shell
/plugin
```

1. **Marketplaces**タブで `lc-semba-ryuichiro/semba-claude-plugins` を追加
2. **Discover**タブで `diagram-drawio` を選択してインストール

### 方法3: チーム設定で自動化

プロジェクトの `.claude/settings.json` に以下を追加すると、チームメンバーに自動でプラグインのインストールを促せます。

```json
{
  "extraKnownMarketplaces": {
    "semba-claude-plugins": {
      "source": {
        "source": "github",
        "repo": "lc-semba-ryuichiro/semba-claude-plugins"
      }
    }
  },
  "enabledPlugins": {
    "diagram-drawio@semba-claude-plugins": true
  }
}
```

## 使い方

### コマンド: `/diagram-drawio`

```text
/diagram-drawio ユーザー認証フローのフローチャートを作成してください
```

```text
/diagram-drawio 以下のアーキテクチャ図を作成:
- フロントエンド (React)
- APIゲートウェイ
- マイクロサービス x 3
- PostgreSQL, Redis
```

### スキル自動起動

以下のようなリクエストで自動的にdraw\.ioスキルが起動します。

- 「draw\.io図を作成して」
- 「フローチャートを作成」
- 「アーキテクチャ図を描いて」
- 「シーケンス図を生成」
- 「ER図を作成」

## 出力例

### ファイル保存

```text
output/
└── authentication-flow.drawio
```

### PNG変換（オプション）

draw\.io CLIがインストールされている場合は、以下のコマンドで変換できます。

```bash
drawio -x -f png -o output.png input.drawio
```

## プラグイン構造

```text
diagram-drawio/
├── .claude-plugin/
│   └── plugin.json          # プラグインマニフェスト
├── commands/
│   └── diagram-drawio.md    # /diagram-drawio コマンド
├── skills/
│   └── diagram-drawio/
│       ├── SKILL.md         # draw.io図作成スキル
│       └── references/
│           ├── aws-icons.md         # AWSアイコン定義
│           ├── design-principles.md # 設計原則
│           └── xml-templates.md     # XMLテンプレート集
└── README.md
```

## 対応図の種類

| 図の種類     | 用途                |
| -------- | ----------------- |
| フローチャート  | 処理フロー、ワークフロー、条件分岐 |
| シーケンス図   | API通信、メッセージシーケンス  |
| アーキテクチャ図 | システム構成、レイヤー構造     |
| ER図      | データベース設計、エンティティ関係 |

## 日本語フォント対応

このプラグインは日本語テキストが正しく表示されるよう、以下の設定を自動適用します。

- `fontFamily=Hiragino Sans` を各要素に明示的に設定
- 日本語テキストは1文字あたり30〜40pxの幅を確保
- フォントサイズ18px（標準の1.5倍）

## トラブルシューティング

| 問題             | 解決策                    |
| -------------- | ---------------------- |
| PNG出力でフォントが変わる | 各要素にfontFamily設定があるか確認 |
| 矢印がノードの上に表示される | XMLで矢印をノードより前に配置       |
| 日本語が途中で改行される   | ノード幅を広げる               |

## ライセンス

MIT License

## 作成者

Ryuichiro Semba
