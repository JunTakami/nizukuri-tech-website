# 株式会社荷造テック 事業紹介サイト

[事業計画.md](../事業計画.md) と [命名候補一覧.md](../命名候補一覧.md) で確定した内容に基づく、事業紹介の静的サイトです。**ブランドガイドライン v1（2026-05-12 確定）適用済み**。

## 構成

- `index.html` — トップ（1ページ完結のシングルページ）
- `style.css` — スタイル（CSS変数で配色・タイポを管理）
- `assets/` — **ブランドアセット**（ロゴ・ファビコン・ロックアップ・OGP・brand-tokens.css）
- `images/` — サイト固有のイラスト（サービスアイコン、ヒーロービジュアル）
- `.nojekyll` — GitHub Pagesで Jekyll 処理をスキップ
- `robots.txt` — 限定公開のため `Disallow: /` を設定（Phase 1 期間中）

## ブランドアセット

[assets/](assets/) にブランドガイドライン v1 の SVG / CSS 一式が格納されています:

| ファイル | 用途 |
|---|---|
| `logo.svg` | ロゴ単体（`currentColor` 対応、対角シアン固定） |
| `logo-mono-white.svg` / `logo-mono-black.svg` | 印刷物用モノクロ版 |
| `logo-lockup-horizontal.svg` / `logo-lockup-vertical.svg` | ロゴ＋社名のロックアップ |
| `favicon.svg` | ブラウザタブ用（角丸ダーク地、16px まで読める） |
| `apple-touch-icon.svg` | iOS ホーム画面用 |
| `ogp.svg` | SNS 共有用 OGP（1200×630）。**PNG 化が必要**（下記） |
| `brand-tokens.css` | カラー・タイポ・スペーシングの CSS 変数（`<head>` で読込済み） |

サイトのヘッダー内のロゴはインラインSVGとして埋め込み（同形）。

## ローカル確認

```bash
cd website
python -m http.server 8000
# ブラウザで http://localhost:8000 を開く
```

## GitHub Pages 公開手順

このディレクトリは GitHub 上の独立 public リポジトリ [`JunTakami/nizukuri-tech-website`](https://github.com/JunTakami/nizukuri-tech-website) で管理。`main` ブランチ root を GitHub Pages のソースに設定済み。push の 30〜90 秒後に https://juntakami.github.io/nizukuri-tech-website/ に反映される。

**現状: 限定公開**（`<meta name="robots" content="noindex, nofollow">` + `robots.txt: Disallow: /`）。Phase 2（年商1,000万到達、新法人化）で解除予定。

## サイト構成（セクション）

1. ヒーロー — 「現役運送業 × AI × 中小最適化。3者を掛け合わせた、不在の存在。」
2. 課題（CHALLENGES）— 4つの典型的な困りごと
3. サービス（SERVICES）— IT相談・自動点呼・セキュリティ・個別開発
4. 強み（WHY US）— 三位一体ポジショニング（軸3 = 完遂責任）
5. 事例（CASES）— 親会社で稼働中の3システム
6. 想い（MESSAGE）— 代表メッセージ
7. お問い合わせ（CONTACT）— メール・電話

## 未完了の項目

- [ ] 電話番号の差し替え（現状「準備中」）
- [ ] メールアドレス（`info@nizukuri-tech.com`）の実取得・運用設定
- [ ] OGP `assets/ogp.svg` の PNG 化（1200×630、`assets/ogp.png` を生成）。SNS 本公開時に必須
- [ ] アクセス解析（Google Analytics等）の判断
- [ ] Phase 2 移行時の noindex / Disallow 解除、ブランド表記の「株式会社荷造テック」切替

## 更新方針

- HTML/CSS が分かる範囲で直接編集できる構造（フレームワーク・ビルドツールなし）
- AI（Claude Code）に「サービス章のテキストを更新して」のような自然文で依頼可能
- ブランドの色・タイポは [assets/brand-tokens.css](assets/brand-tokens.css) を一次ソースとして参照。style.css の `:root` は既存変数名で値を踏襲（ブリッジ方式）
