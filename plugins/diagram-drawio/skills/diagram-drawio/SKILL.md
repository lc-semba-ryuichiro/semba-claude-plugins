# draw\.io図作成ガイドライン

draw\.io（diagrams.net）のXML形式で図を作成するためのスキル。フローチャート、シーケンス図、アーキテクチャ図、ER図、AWSアーキテクチャ図など複数種類の図に対応し、PNG出力でも正しく表示される高品質な図を生成する。「draw\.io図を作成」「drawio XMLを生成」「フローチャートを作成」「アーキテクチャ図を作成」「シーケンス図を作成」「AWS構成図を作成」などのリクエストで使用する。 (project)

## 目次

- [事前準備チェックリスト](#事前準備チェックリスト)
- [図の設計原則](#図の設計原則)
  - [段階的開示（Progressive Disclosure）](#段階的開示progressive-disclosure)
  - [図の種類と用途](#図の種類と用途)
  - [シンプルさの原則](#シンプルさの原則)
- [凡例ルール](#凡例ルール)
  - [線のスタイル](#線のスタイル)
  - [矢印の方向](#矢印の方向)
  - [色の意味（統一ルール）](#色の意味統一ルール)
- [メタデータ](#メタデータ)
  - [推奨メタデータ](#推奨メタデータ)
- [必須ルール](#必須ルール)
  - [1. フォント設定（最重要）](#1-フォント設定最重要)
  - [2. 矢印の配置（背面配置）](#2-矢印の配置背面配置)
  - [3. テキストサイズと余白](#3-テキストサイズと余白)
- [図の種類別ガイドライン](#図の種類別ガイドライン)
  - [フローチャート](#フローチャート)
  - [シーケンス図](#シーケンス図)
  - [アーキテクチャ図](#アーキテクチャ図)
  - [ER図](#er図)
- [スタイル設定テンプレート](#スタイル設定テンプレート)
  - [基本ノード](#基本ノード)
  - [矢印スタイル](#矢印スタイル)
- [完全なXMLテンプレート](#完全なxmlテンプレート)
- [出力方法](#出力方法)
- [よくある問題と対処法](#よくある問題と対処法)

## 事前準備チェックリスト

図を作成する前に以下を確認する。

- [ ] 目的の明確化: この図で何を伝えたいか？
- [ ] 対象者の特定: 誰が見る図か？（技術者 / 非技術者 / 経営層）
- [ ] 抽象度の決定: どの程度の詳細が必要か？
- [ ] 図の種類選択: 目的に最も合う図の種類は？

***

## 図の設計原則

### 段階的開示（Progressive Disclosure）

複雑なシステムは階層化して表現する。

```text
Context図（全体俯瞰）
    ↓
System図（主要コンポーネント）
    ↓
Component図（詳細構成）
    ↓
Sequence図（処理フロー）
```

### 図の種類と用途

| 図の種類     | 用途          | 対象者        |
| -------- | ----------- | ---------- |
| Context図 | システム境界と外部連携 | 経営層、PM     |
| アーキテクチャ図 | 技術構成の全体像    | 技術者、アーキテクト |
| シーケンス図   | 処理の時系列フロー   | 開発者        |
| フローチャート  | 業務/処理フロー    | 全員         |
| ER図      | データ構造       | 開発者、DBA    |

### シンプルさの原則

- 1つの図に詰め込みすぎない
- 1図1目的を心がける
- 詳細は別図に分離する

***

## 凡例ルール

### 線のスタイル

| スタイル | 意味          | XMLスタイル         |
| ---- | ----------- | --------------- |
| 実線   | 同期通信、直接呼び出し | `dashed=0`      |
| 破線   | 非同期通信、イベント  | `dashed=1`      |
| 太線   | 主要フロー       | `strokeWidth=2` |

### 矢印の方向

- 矢印はデータや制御の流れ方向を示す。
- 双方向は避け、単方向矢印×2で表現

### 色の意味（統一ルール）

| 色   | 意味                    |
| --- | --------------------- |
| 青系  | エントリーポイント、API、フロントエンド |
| 緑系  | 処理、サービス、バックエンド        |
| 黄系  | データ、ストレージ、条件分岐        |
| 赤系  | エラー、警告、重要             |
| 紫系  | 外部連携、サードパーティ          |
| グレー | 境界、グループ、ベース           |

***

## メタデータ

図にはメタデータを含める。

```xml
<diagram name="[タイトル] - v1.0 - 2025-01-15" id="unique-id">
```

### 推奨メタデータ

- タイトル: 図の目的を表す名前
- バージョン: v1.0, v1.1など
- 更新日: YYYY-MM-DD形式
- 作成者:（コメントで記載）

***

## 必須ルール

### 1. フォント設定（最重要）

**`defaultFontFamily`だけでは不十分。各テキスト要素に明示的に`fontFamily`を追加する。**

```xml
<!-- mxGraphModelにデフォルトフォントを設定 -->
<mxGraphModel defaultFontFamily="Hiragino Sans" ...>

<!-- 各テキスト要素にも明示的に設定 -->
<mxCell value="テキスト" style="...;fontFamily=Hiragino Sans;..." />
```

**推奨フォント:**

- 日本語: `Hiragino Sans`, `Noto Sans JP`, `Yu Gothic`
- 英語: `Helvetica`, `Arial`

### 2. 矢印の配置（背面配置）

**矢印はXMLの先頭（root直下の最初）に配置する。** これにより、矢印が他の要素の背面に表示される。

```xml
<root>
  <mxCell id="0"/>
  <mxCell id="1" parent="0"/>

  <!-- 矢印を先に配置（最背面） -->
  <mxCell id="arrow1" style="edgeStyle=..." edge="1" .../>
  <mxCell id="arrow2" style="edgeStyle=..." edge="1" .../>

  <!-- その後にノードを配置（前面） -->
  <mxCell id="node1" style="rounded=..." vertex="1" .../>
  <mxCell id="node2" style="rounded=..." vertex="1" .../>
</root>
```

### 3. テキストサイズと余白

| 要素        | 推奨設定                |
| --------- | ------------------- |
| フォントサイズ   | 標準の1.5倍（18px程度）     |
| 日本語テキスト   | 1文字あたり約30-40pxの幅を確保 |
| 矢印とラベルの距離 | 最低20px以上            |

***

## 図の種類別ガイドライン

### フローチャート

- 開始/終了: 角丸矩形（fillColor=#dae8fc, strokeColor=#6c8ebf）
- 処理: 矩形（fillColor=#d5e8d4, strokeColor=#82b366）
- 条件分岐: ダイアモンド（fillColor=#fff2cc, strokeColor=#d6b656）
- 入出力: 平行四辺形

### シーケンス図

- アクター: stickman形状
- ライフライン: 縦の破線
- メッセージ: 水平矢印（ラベル付き）

### アーキテクチャ図

- コンポーネント間の距離: 最低50px
- グループ化: swimlaneまたはcontainer使用
- 色分け: レイヤーごとに統一した配色

### ER図

- エンティティ: 矩形（タイトル行 + 属性リスト）
- リレーションシップ: ダイアモンドor線のみ
- カーディナリティ: 矢印のスタイルで表現

***

## スタイル設定テンプレート

### 基本ノード

```xml
<!-- 角丸矩形 -->
<mxCell value="処理" style="rounded=1;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- ダイアモンド（条件分岐） -->
<mxCell value="条件" style="rhombus;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="200" width="80" height="80" as="geometry"/>
</mxCell>
```

### 矢印スタイル

```xml
<!-- 基本矢印 -->
<mxCell style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1" source="node1" target="node2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

***

## 完全なXMLテンプレート

詳細は `references/xml-templates.md` を参照。

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Page-1" id="diagram1">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- 矢印（最背面）-->
        <!-- ノード（前面）-->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

***

## 出力方法

1. **.drawioファイルとして保存**: プロジェクト内に保存し、draw\.ioで編集可能
2. **ターミナル出力**: XMLをコピーしてdraw\.ioに貼り付け可能

**PNG変換コマンド**:

```bash
drawio -x -f png -o output.png input.drawio
```

***

## よくある問題と対処法

| 問題             | 原因             | 対処法                  |
| -------------- | -------------- | -------------------- |
| PNG出力でフォントが変わる | fontFamilyが未設定 | 各要素に明示的にfontFamily設定 |
| 矢印がノードの上に表示される | XMLの記述順序       | 矢印をXML先頭に移動          |
| 日本語が途中で改行される   | 幅が不足           | ノード幅を広げる（1文字30-40px） |
| ラベルが矢印と重なる     | 間隔が狭い          | 20px以上の距離を確保         |
