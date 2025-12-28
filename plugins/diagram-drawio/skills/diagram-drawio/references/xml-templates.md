# draw\.io XMLテンプレート集

## 目次

- [基本構造](#基本構造)
- [フローチャートテンプレート](#フローチャートテンプレート)
- [シーケンス図テンプレート](#シーケンス図テンプレート)
- [アーキテクチャ図テンプレート](#アーキテクチャ図テンプレート)
- [ER図テンプレート](#er図テンプレート)
- [カラーパレット](#カラーパレット)
  - [標準色（draw.io デフォルト）](#標準色drawio-デフォルト)
  - [レイヤー色（アーキテクチャ図用）](#レイヤー色アーキテクチャ図用)
- [形状リファレンス](#形状リファレンス)
  - [基本形状](#基本形状)
  - [矢印スタイル](#矢印スタイル)
- [メタデータ付きテンプレート](#メタデータ付きテンプレート)
  - [メタデータ属性](#メタデータ属性)
- [凡例テンプレート](#凡例テンプレート)
- [PNG出力確認コマンド](#png出力確認コマンド)
  - [オプション](#オプション)

## 基本構造

すべてのdraw\.io XMLは以下の基本構造に従う。

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Page-1" id="unique-diagram-id">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- コンテンツはここに配置 -->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

***

## フローチャートテンプレート

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Flowchart" id="flowchart-1">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>

        <!-- 矢印（最背面） -->
        <mxCell id="edge-1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1" source="start" target="process1">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="edge-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1" source="process1" target="decision1">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="edge-3" value="Yes" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1" source="decision1" target="process2">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="edge-4" value="No" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1" source="decision1" target="end">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="edge-5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1" source="process2" target="end">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>

        <!-- ノード（前面） -->
        <mxCell id="start" value="開始" style="rounded=1;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
          <mxGeometry x="340" y="40" width="120" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="process1" value="処理1" style="rounded=0;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="340" y="140" width="120" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="decision1" value="条件?" style="rhombus;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;fillColor=#fff2cc;strokeColor=#d6b656;" vertex="1" parent="1">
          <mxGeometry x="350" y="240" width="100" height="100" as="geometry"/>
        </mxCell>
        <mxCell id="process2" value="処理2" style="rounded=0;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="500" y="260" width="120" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="end" value="終了" style="rounded=1;whiteSpace=wrap;html=1;fontSize=18;fontFamily=Hiragino Sans;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
          <mxGeometry x="340" y="400" width="120" height="60" as="geometry"/>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

***

## シーケンス図テンプレート

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Sequence" id="sequence-1">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>

        <!-- ライフライン（背面） -->
        <mxCell id="lifeline1" style="html=1;points=[];perimeter=orthogonalPerimeter;dashed=1;strokeColor=#666666;" edge="1" parent="1">
          <mxGeometry x="150" y="80" width="1" height="300" as="geometry">
            <mxPoint x="150" y="80" as="sourcePoint"/>
            <mxPoint x="150" y="380" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="lifeline2" style="html=1;points=[];perimeter=orthogonalPerimeter;dashed=1;strokeColor=#666666;" edge="1" parent="1">
          <mxGeometry x="350" y="80" width="1" height="300" as="geometry">
            <mxPoint x="350" y="80" as="sourcePoint"/>
            <mxPoint x="350" y="380" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="lifeline3" style="html=1;points=[];perimeter=orthogonalPerimeter;dashed=1;strokeColor=#666666;" edge="1" parent="1">
          <mxGeometry x="550" y="80" width="1" height="300" as="geometry">
            <mxPoint x="550" y="80" as="sourcePoint"/>
            <mxPoint x="550" y="380" as="targetPoint"/>
          </mxGeometry>
        </mxCell>

        <!-- メッセージ（矢印） -->
        <mxCell id="msg1" value="1. リクエスト" style="html=1;verticalAlign=bottom;endArrow=block;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1">
          <mxGeometry x="150" y="120" width="200" as="geometry">
            <mxPoint x="150" y="120" as="sourcePoint"/>
            <mxPoint x="350" y="120" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="msg2" value="2. データ取得" style="html=1;verticalAlign=bottom;endArrow=block;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1">
          <mxGeometry x="350" y="160" width="200" as="geometry">
            <mxPoint x="350" y="160" as="sourcePoint"/>
            <mxPoint x="550" y="160" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="msg3" value="3. データ返却" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1">
          <mxGeometry x="350" y="200" width="200" as="geometry">
            <mxPoint x="550" y="200" as="sourcePoint"/>
            <mxPoint x="350" y="200" as="targetPoint"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="msg4" value="4. レスポンス" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;fontSize=14;fontFamily=Hiragino Sans;" edge="1" parent="1">
          <mxGeometry x="150" y="240" width="200" as="geometry">
            <mxPoint x="350" y="240" as="sourcePoint"/>
            <mxPoint x="150" y="240" as="targetPoint"/>
          </mxGeometry>
        </mxCell>

        <!-- アクター/オブジェクト（前面） -->
        <mxCell id="actor1" value="クライアント" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;fontSize=14;fontFamily=Hiragino Sans;" vertex="1" parent="1">
          <mxGeometry x="135" y="20" width="30" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="object1" value="サーバー" style="rounded=0;whiteSpace=wrap;html=1;fontSize=14;fontFamily=Hiragino Sans;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
          <mxGeometry x="300" y="30" width="100" height="40" as="geometry"/>
        </mxCell>
        <mxCell id="object2" value="データベース" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fontSize=14;fontFamily=Hiragino Sans;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="510" y="20" width="80" height="60" as="geometry"/>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

***

## アーキテクチャ図テンプレート

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Architecture" id="architecture-1">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>

        <!-- 矢印（最背面） -->
        <mxCell id="conn1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;strokeWidth=2;" edge="1" parent="1" source="frontend" target="api">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="conn2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;strokeWidth=2;" edge="1" parent="1" source="api" target="service1">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="conn3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;strokeWidth=2;" edge="1" parent="1" source="api" target="service2">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="conn4" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;strokeWidth=2;" edge="1" parent="1" source="service1" target="db">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="conn5" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;fontSize=14;fontFamily=Hiragino Sans;strokeWidth=2;" edge="1" parent="1" source="service2" target="cache">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>

        <!-- レイヤーグループ -->
        <mxCell id="layer-presentation" value="Presentation Layer" style="swimlane;horizontal=1;fontSize=16;fontFamily=Hiragino Sans;fillColor=#f5f5f5;strokeColor=#666666;" vertex="1" parent="1">
          <mxGeometry x="40" y="40" width="720" height="100" as="geometry"/>
        </mxCell>
        <mxCell id="layer-application" value="Application Layer" style="swimlane;horizontal=1;fontSize=16;fontFamily=Hiragino Sans;fillColor=#e1f5fe;strokeColor=#0288d1;" vertex="1" parent="1">
          <mxGeometry x="40" y="160" width="720" height="100" as="geometry"/>
        </mxCell>
        <mxCell id="layer-service" value="Service Layer" style="swimlane;horizontal=1;fontSize=16;fontFamily=Hiragino Sans;fillColor=#e8f5e9;strokeColor=#388e3c;" vertex="1" parent="1">
          <mxGeometry x="40" y="280" width="720" height="100" as="geometry"/>
        </mxCell>
        <mxCell id="layer-data" value="Data Layer" style="swimlane;horizontal=1;fontSize=16;fontFamily=Hiragino Sans;fillColor=#fff3e0;strokeColor=#f57c00;" vertex="1" parent="1">
          <mxGeometry x="40" y="400" width="720" height="100" as="geometry"/>
        </mxCell>

        <!-- コンポーネント（前面） -->
        <mxCell id="frontend" value="Frontend&#10;(React)" style="rounded=1;whiteSpace=wrap;html=1;fontSize=14;fontFamily=Hiragino Sans;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="layer-presentation">
          <mxGeometry x="280" y="35" width="160" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="api" value="API Gateway" style="rounded=1;whiteSpace=wrap;html=1;fontSize=14;fontFamily=Hiragino Sans;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="layer-application">
          <mxGeometry x="280" y="35" width="160" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="service1" value="User Service" style="rounded=1;whiteSpace=wrap;html=1;fontSize=14;fontFamily=Hiragino Sans;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="layer-service">
          <mxGeometry x="120" y="35" width="140" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="service2" value="Order Service" style="rounded=1;whiteSpace=wrap;html=1;fontSize=14;fontFamily=Hiragino Sans;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="layer-service">
          <mxGeometry x="460" y="35" width="140" height="50" as="geometry"/>
        </mxCell>
        <mxCell id="db" value="PostgreSQL" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fontSize=14;fontFamily=Hiragino Sans;fillColor=#fff2cc;strokeColor=#d6b656;" vertex="1" parent="layer-data">
          <mxGeometry x="150" y="25" width="100" height="60" as="geometry"/>
        </mxCell>
        <mxCell id="cache" value="Redis" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fontSize=14;fontFamily=Hiragino Sans;fillColor=#fff2cc;strokeColor=#d6b656;" vertex="1" parent="layer-data">
          <mxGeometry x="480" y="25" width="100" height="60" as="geometry"/>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

***

## ER図テンプレート

```xml
<mxfile host="app.diagrams.net">
  <diagram name="ER Diagram" id="er-1">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>

        <!-- リレーション（最背面） -->
        <mxCell id="rel1" value="1" style="endArrow=none;html=1;rounded=0;fontSize=14;fontFamily=Hiragino Sans;startArrow=ERone;startFill=0;endFill=0;endSize=12;startSize=12;" edge="1" parent="1" source="users" target="orders">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="rel1-label" value="n" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=14;fontFamily=Hiragino Sans;" vertex="1" connectable="0" parent="rel1">
          <mxGeometry x="0.8" relative="1" as="geometry">
            <mxPoint x="-10" y="10" as="offset"/>
          </mxGeometry>
        </mxCell>
        <mxCell id="rel2" value="n" style="endArrow=none;html=1;rounded=0;fontSize=14;fontFamily=Hiragino Sans;startArrow=ERmany;startFill=0;endFill=0;endSize=12;startSize=12;" edge="1" parent="1" source="orders" target="products">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        <mxCell id="rel2-label" value="m" style="edgeLabel;html=1;align=center;verticalAlign=middle;resizable=0;points=[];fontSize=14;fontFamily=Hiragino Sans;" vertex="1" connectable="0" parent="rel2">
          <mxGeometry x="0.8" relative="1" as="geometry">
            <mxPoint x="-10" y="10" as="offset"/>
          </mxGeometry>
        </mxCell>

        <!-- エンティティ（前面） -->
        <mxCell id="users" value="Users" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=30;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=0;marginBottom=0;fontSize=14;fontFamily=Hiragino Sans;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
          <mxGeometry x="80" y="120" width="160" height="120" as="geometry"/>
        </mxCell>
        <mxCell id="users-pk" value="+ id: INT (PK)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;fontStyle=4;" vertex="1" parent="users">
          <mxGeometry y="30" width="160" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="users-name" value="  name: VARCHAR(100)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="users">
          <mxGeometry y="60" width="160" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="users-email" value="  email: VARCHAR(255)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="users">
          <mxGeometry y="90" width="160" height="30" as="geometry"/>
        </mxCell>

        <mxCell id="orders" value="Orders" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=30;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=0;marginBottom=0;fontSize=14;fontFamily=Hiragino Sans;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="320" y="120" width="160" height="120" as="geometry"/>
        </mxCell>
        <mxCell id="orders-pk" value="+ id: INT (PK)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;fontStyle=4;" vertex="1" parent="orders">
          <mxGeometry y="30" width="160" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="orders-fk" value="  user_id: INT (FK)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="orders">
          <mxGeometry y="60" width="160" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="orders-total" value="  total: DECIMAL(10,2)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="orders">
          <mxGeometry y="90" width="160" height="30" as="geometry"/>
        </mxCell>

        <mxCell id="products" value="Products" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=30;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=0;marginBottom=0;fontSize=14;fontFamily=Hiragino Sans;fillColor=#fff2cc;strokeColor=#d6b656;" vertex="1" parent="1">
          <mxGeometry x="560" y="120" width="160" height="120" as="geometry"/>
        </mxCell>
        <mxCell id="products-pk" value="+ id: INT (PK)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;fontStyle=4;" vertex="1" parent="products">
          <mxGeometry y="30" width="160" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="products-name" value="  name: VARCHAR(200)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="products">
          <mxGeometry y="60" width="160" height="30" as="geometry"/>
        </mxCell>
        <mxCell id="products-price" value="  price: DECIMAL(10,2)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=top;spacingLeft=4;spacingRight=4;overflow=hidden;rotatable=0;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="products">
          <mxGeometry y="90" width="160" height="30" as="geometry"/>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

***

## カラーパレット

### 標準色（draw\.io デフォルト）

| 用途            | fillColor | strokeColor |
| ------------- | --------- | ----------- |
| 青系（開始/終了、API） | #dae8fc   | #6c8ebf     |
| 緑系（処理、サービス）   | #d5e8d4   | #82b366     |
| 黄系（条件、データ）    | #fff2cc   | #d6b656     |
| 赤系（エラー、警告）    | #f8cecc   | #b85450     |
| 紫系（外部連携）      | #e1d5e7   | #9673a6     |
| グレー（ベース、境界）   | #f5f5f5   | #666666     |

### レイヤー色（アーキテクチャ図用）

| レイヤー         | fillColor | strokeColor |
| ------------ | --------- | ----------- |
| Presentation | #f5f5f5   | #666666     |
| Application  | #e1f5fe   | #0288d1     |
| Service      | #e8f5e9   | #388e3c     |
| Data         | #fff3e0   | #f57c00     |

***

## 形状リファレンス

### 基本形状

| 形状        | style                                                                              |
| --------- | ---------------------------------------------------------------------------------- |
| 角丸矩形      | `rounded=1;whiteSpace=wrap;html=1;`                                                |
| 矩形        | `rounded=0;whiteSpace=wrap;html=1;`                                                |
| ダイアモンド    | `rhombus;whiteSpace=wrap;html=1;`                                                  |
| 円         | `ellipse;whiteSpace=wrap;html=1;`                                                  |
| 円柱（DB）    | `shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;` |
| 人型（Actor） | `shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;`            |
| スイムレーン    | `swimlane;horizontal=1;`                                                           |

### 矢印スタイル

| タイプ       | style                                                                             |
| --------- | --------------------------------------------------------------------------------- |
| 直交矢印      | `edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;` |
| 直線矢印      | `html=1;verticalAlign=bottom;endArrow=block;`                                     |
| 破線矢印      | `html=1;verticalAlign=bottom;endArrow=open;dashed=1;`                             |
| ER関連（1対多） | `endArrow=none;html=1;rounded=0;startArrow=ERone;startFill=0;endFill=0;`          |

***

## メタデータ付きテンプレート

図にはメタデータを含めることを推奨する。

```xml
<mxfile host="app.diagrams.net" modified="YYYY-MM-DDTHH:MM:SS.000Z" agent="Claude Code" version="1.0">
  <diagram name="システム構成図 - v1.0 - YYYY-MM-DD" id="system-arch-v1">
    <mxGraphModel dx="1434" dy="836" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0" defaultFontFamily="Hiragino Sans">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- 図の内容 -->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

### メタデータ属性

| 属性       | 説明                  | 例                             |
| -------- | ------------------- | ----------------------------- |
| name     | 図のタイトル + バージョン + 日付 | `システム構成図 - v1.0 - YYYY-MM-DD` |
| modified | 最終更新日時（ISO 8601）    | `YYYY-MM-DDTHH:MM:SS.000Z`    |
| agent    | 作成ツール               | `Claude Code`                 |
| version  | 図のバージョン             | `1.0`                         |

***

## 凡例テンプレート

図には凡例を含めることを推奨する。

```xml
<!-- 凡例コンテナ -->
<mxCell id="legend" value="凡例" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=26;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=0;marginBottom=0;fontSize=14;fontFamily=Hiragino Sans;fillColor=#f5f5f5;strokeColor=#666666;" vertex="1" parent="1">
  <mxGeometry x="620" y="400" width="180" height="140" as="geometry"/>
</mxCell>

<!-- 同期通信 -->
<mxCell id="legend-sync-label" value="同期通信" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="legend">
  <mxGeometry y="26" width="90" height="26" as="geometry"/>
</mxCell>
<mxCell id="legend-sync-line" style="endArrow=block;html=1;rounded=0;strokeWidth=1;dashed=0;" edge="1" parent="legend">
  <mxGeometry width="50" height="50" relative="1" as="geometry">
    <mxPoint x="95" y="39" as="sourcePoint"/>
    <mxPoint x="165" y="39" as="targetPoint"/>
  </mxGeometry>
</mxCell>

<!-- 非同期通信 -->
<mxCell id="legend-async-label" value="非同期通信" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="legend">
  <mxGeometry y="52" width="90" height="26" as="geometry"/>
</mxCell>
<mxCell id="legend-async-line" style="endArrow=block;html=1;rounded=0;strokeWidth=1;dashed=1;" edge="1" parent="legend">
  <mxGeometry width="50" height="50" relative="1" as="geometry">
    <mxPoint x="95" y="65" as="sourcePoint"/>
    <mxPoint x="165" y="65" as="targetPoint"/>
  </mxGeometry>
</mxCell>

<!-- データフロー -->
<mxCell id="legend-data-label" value="データフロー" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="legend">
  <mxGeometry y="78" width="90" height="26" as="geometry"/>
</mxCell>
<mxCell id="legend-data-line" style="endArrow=classic;html=1;rounded=0;strokeWidth=2;strokeColor=#666666;" edge="1" parent="legend">
  <mxGeometry width="50" height="50" relative="1" as="geometry">
    <mxPoint x="95" y="91" as="sourcePoint"/>
    <mxPoint x="165" y="91" as="targetPoint"/>
  </mxGeometry>
</mxCell>

<!-- エラーフロー -->
<mxCell id="legend-error-label" value="エラー" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;fontSize=12;fontFamily=Hiragino Sans;" vertex="1" parent="legend">
  <mxGeometry y="104" width="90" height="26" as="geometry"/>
</mxCell>
<mxCell id="legend-error-line" style="endArrow=block;html=1;rounded=0;strokeWidth=1;strokeColor=#b85450;" edge="1" parent="legend">
  <mxGeometry width="50" height="50" relative="1" as="geometry">
    <mxPoint x="95" y="117" as="sourcePoint"/>
    <mxPoint x="165" y="117" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

***

## PNG出力確認コマンド

生成した図をPNG出力して確認する。

```bash
# 基本的なPNG出力
drawio -x -f png -o output.png input.drawio

# 高解像度出力（スケール2倍、透過背景）
drawio -x -f png -s 2 -t -o output.png input.drawio

# 特定ページのみ出力
drawio -x -f png -p 0 -o output.png input.drawio
```

### オプション

| オプション    | 説明           |
| -------- | ------------ |
| `-x`     | エクスポートモード    |
| `-f png` | PNG形式で出力     |
| `-s 2`   | スケール2倍       |
| `-t`     | 透過背景         |
| `-p 0`   | ページ指定（0から開始） |
| `-o`     | 出力ファイル名      |
