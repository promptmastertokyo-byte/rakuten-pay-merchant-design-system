# Rakuten Pay Merchant Design System

楽天ペイ加盟店向けコンソールを想定した、管理画面用デザインシステムのプロトタイプです。

店舗オーナー、店頭スタッフ、本部管理者が、売上・入金・審査状況を素早く確認し、取消や返金などの金銭操作を安全に実行できることを目的にしています。

> [!NOTE]
> 本リポジトリはデザイン検討・プロトタイプ用途の成果物です。

## 特徴

- ビルド不要で閲覧できる、単一HTMLのデザインシステム仕様書
- Light / Darkテーマ対応
- W3C Design Tokens Community Group（DTCG）形式のデザイントークン
- Tokens Studio for Figma / Figma Variablesへの展開を想定
- Style Dictionaryを介したCSS Custom Properties / Storybookへの展開を想定
- WCAG 2.1 AAを最低基準としたアクセシビリティ方針
- 金額、取引、入金、店舗切り替えなど加盟店ドメイン固有のUIを収録

## 収録内容

### Design Principles

- デザイン原則：現場速度、可逆性の可視化、一つの語彙
- UX原則：サマリーが先、色だけに頼らない、待機状態の可視化
- ブランド原則：クリムゾンの用途制限、実務的な信頼感、可読性

### Foundations

- Color（Primitive / Semantic、Light / Dark）
- Typography
- Spacing / Radius
- Elevation / Border
- Iconography
- Motion / Reduced Motion
- Breakpoints / Responsive Rules

### Components

31種類のコンポーネントを、用途、構造、状態、使用ルール、Do / Don'tとともに掲載しています。

- 入力・操作：Button、Text Field、Select、Checkbox、Radio、Switch、Search、Filter、Pagination、Tooltip
- ステータス・ラベル：Badge、Chip、Tag、Amount Display
- レイアウト・ナビゲーション：Card、Table、Tabs、Sidebar、Header、Breadcrumb
- オーバーレイ・フィードバック：Modal、Drawer、Toast、Empty State、Error State、Loading、Confirm Dialog
- 加盟店固有：Store Switcher、Deposit Summary Card、Date Range Picker、Transaction Row、NumPad、Receipt Preview

### Patterns

Form、Search、CRUD、Dashboard、List、Detail、Wizard、Authentication、Payment、Notificationの画面パターンを収録しています。

## ファイル構成

```text
.
├── index.html          # デザインシステムのドキュメントとUIプレビュー
└── design-tokens.json  # DTCG形式のデザイントークン（Source of Truth）
```

## 閲覧方法

ビルドや依存パッケージのインストールは不要です。

1. リポジトリをクローンします。
2. `index.html`をブラウザで開きます。

```bash
git clone https://github.com/promptmastertokyo-byte/rakuten-pay-merchant-design-system.git
cd rakuten-pay-merchant-design-system
open index.html
```

macOS以外では、ファイルマネージャーから`index.html`をブラウザで開いてください。

## デザイントークン

`design-tokens.json`をトークンの唯一の正本として扱います。主なグループは次のとおりです。

- `color.primitive`：色の基礎パレット
- `color.semantic.light` / `color.semantic.dark`：テーマ別の意味トークン
- `typography`：UI書体、データ書体、タイプスケール
- `spacing` / `radius` / `shadow` / `border`：レイアウトと外観
- `icon` / `motion` / `breakpoint`：アイコン、動き、レスポンシブ

Tokens Studioでは、`color.semantic.light`と`color.semantic.dark`を単一のVariable Collectionに対するLight / Darkの2 Modeとして設定してください。

## 更新ルール

1. `design-tokens.json`を先に更新する。
2. `index.html`内のCSS Custom Propertiesと埋め込みJSONを同期する。
3. Light / Darkの両テーマで表示を確認する。
4. 通常テキストのコントラスト比4.5:1以上を確認する。
5. キーボード操作、フォーカス表示、Reduced Motionを確認する。

## アクセシビリティ方針

- WCAG 2.1 AAを最低基準とする
- 状態を色だけで伝えず、色・アイコン・テキストを併用する
- すべての操作をキーボードで完結可能にする
- フォーカスリングを常に視認可能にする
- `prefers-reduced-motion`に応じてアニメーションを抑制する
- 破壊的操作では非破壊側を既定フォーカスにする

## 技術構成

- HTML
- CSS Custom Properties
- Vanilla JavaScript
- JSON（W3C DTCG形式）

外部ライブラリやビルドツールには依存していません。
