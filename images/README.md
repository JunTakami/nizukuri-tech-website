# AI生成画像 必要リスト

サイト初版に追加で必要な画像をまとめます。生成は別途（ChatGPT 画像生成、Midjourney、Adobe Firefly等）。

## 必須

### 1. ヒーローセクションの背景／装飾画像
- ファイル名候補: `hero-bg.png` / `hero-illust.png`
- 用途: トップヒーローの背景または右側装飾
- 推奨サイズ: 1600×900 px（16:9、必要に応じて切り抜き）
- 想定トーン: 浜松の港・運送・テクノロジーをモチーフ。落ち着いた青〜オレンジのグラデーション。写実的すぎず、抽象寄り
- プロンプト例: "minimalist abstract illustration of a logistics truck silhouette merging with a network of digital lines, sunset colors over a Japanese coastal town, calm and trustworthy mood"

### 2. ロゴ
- ファイル名: `logo.svg`（推奨）または `logo.png`
- 用途: ヘッダー左上（現状はテキストブランド）
- 推奨サイズ: SVGならスケーラブル、PNGなら 200×60 px 程度
- 想定トーン: シンプル、モノクロまたは2色、漢字「荷造テック」または「Nizukuri Tech」

### 3. OGP用シェア画像
- ファイル名: `og-image.png`
- 用途: SNSシェア時のサムネイル（Facebook/X/LINE等）
- 必須サイズ: 1200×630 px
- 内容: ロゴ + キャッチコピー「現役運送業 × AI × 中小最適化」

### 4. favicon
- ファイル名: `favicon.ico` または `favicon.svg`
- 用途: ブラウザタブのアイコン
- サイズ: 32×32 px / 48×48 px

## あると望ましい

### 5. 各サービスカードのアイコン（5枚）
- ファイル名: `icon-consult.svg`, `icon-tenko.svg`, `icon-haisha.svg`, `icon-security.svg`, `icon-dev.svg`
- 用途: サービス章の各カード見出し横
- サイズ: 48×48 px 程度
- 想定トーン: 線画アイコン、グレー〜ネイビー単色

### 6. 事例カードのスクリーンショット風画像（3枚）
- ファイル名: `case-shukkin.png`, `case-tenko.png`, `case-security.png`
- 用途: 事例章の各カード上部
- サイズ: 800×450 px (16:9)
- 想定トーン: ダッシュボードのモックアップ、運送業らしいデータが入った画面

## 配置後の HTML 修正

画像を配置したら、`index.html` の以下を修正:

- ヒーローに `<img src="images/hero-illust.png" alt="">` を追加するか、CSSで `.hero { background-image: url(images/hero-bg.png); }` を設定
- ヘッダーの `.brand` をテキストからロゴ画像に差し替え
- `<head>` に `<link rel="icon" href="images/favicon.svg">` を追加
- `<head>` の `<meta property="og:image">` を追加し `images/og-image.png` を指定

## 著作権・利用注意

- AI生成画像は商用利用可能なツール／ライセンスを使用すること
- 親会社（日本荷造運送）のロゴ・建物写真などを流用する場合は必ず親会社に確認
