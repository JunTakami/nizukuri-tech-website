# 画像アセット

サイトで使用する画像。AI生成ラスター画像の代わりに、テクノ・ミニマルのサイトデザインに合わせて**手書きSVG**で揃えています（2026-04-30）。

## 配置済みアセット

### ロゴ・ファビコン

| ファイル | 用途 | 備考 |
|---|---|---|
| `logo.svg` | （参考用 単体ファイル） | サイト本体ではヘッダー内にインラインSVGとして埋め込み |
| `favicon.svg` | ブラウザタブ | `<link rel="icon" href="images/favicon.svg" type="image/svg+xml">` で参照 |

### サービスアイコン

| ファイル | 紐づくサービス |
|---|---|
| `icons/consult.svg` | SVC.001 IT相談（吹き出し+三点） |
| `icons/tenko.svg` | SVC.002 自動点呼の運用支援（円+チェック） |
| `icons/haisha.svg` | SVC.003 配車・出勤管理（トラック） |
| `icons/security.svg` | SVC.004 セキュリティチェック対応（盾+チェック） |
| `icons/dev.svg` | SVC.005 個別開発・運用支援（コードブラケット） |

サービスアイコンも本体にはインラインSVGとして埋め込んでいます。`stroke="currentColor"` を使っているのでCSS側で `color: var(--cyan)` を当てて発色を制御しています。

### OGP画像

`og-image.svg` (1200×630) — SNSシェア時のサムネイル用。

**⚠️ PNG変換が必要**: 多くのSNS（X、Facebook、LINE等）はOGP画像にSVGを受け付けません。本公開時に以下のいずれかの方法で `og-image.png` を作成してください:

1. **オンライン変換**: https://cloudconvert.com/svg-to-png （1200×630で出力）
2. **ブラウザ**: SVGをChromeで開いて DevTools → Capture full size screenshot
3. **Inkscape/Affinity Designer等のローカルツール**

`index.html` の OGP メタタグは既に `images/og-image.png` を参照する形にしてあるので、PNG化したファイルを置けば自動的に反映されます。

## ロゴデザインの意図

- **外枠の正方形** — 「荷造（パッケージ）」を象徴
- **内側の三本線** — 「三位一体（現役運送業 × AI × 中小最適化）」と日本語の「三」
- **下段だけシアン** — 一番下が「AI×小回り体制」軸であり、テック寄りである象徴
- **モノラインのfeather風** — 親会社（運送業）の信頼感とテックの先進性のバランス

## ラスター画像（写真・イラスト）の追加について

写実的な画像（浜松の風景、トラック写真、スタッフ写真など）を後追いで足したい場合:

1. AI画像生成ツール（ChatGPT、Midjourney、Adobe Firefly等）でPNG/JPGを生成
2. このディレクトリに配置（例: `hero-bg.png`, `staff.jpg`）
3. `index.html` および `style.css` に `<img>` タグまたは `background-image` で組み込み
4. 商用利用可能なライセンスを必ず確認

ただし現状のテクノ・ミニマル設計は**写真を入れない方が一貫性が保てる**ため、写真追加は慎重に検討してください。
