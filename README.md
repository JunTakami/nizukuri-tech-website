# 株式会社荷造テック 事業紹介サイト

[事業計画.md](../事業計画.md) と [命名候補一覧.md](../命名候補一覧.md) で確定した内容に基づく、事業紹介の静的サイトです。

## 構成

- `index.html` — トップ（1ページ完結のシングルページ）
- `style.css` — スタイル（CSS変数で配色を管理）
- `.nojekyll` — GitHub Pagesで Jekyll 処理をスキップ
- `images/` — AI生成画像を後から配置するディレクトリ
- `images/README.md` — 必要な画像のリスト

## ローカル確認

```bash
cd website
python -m http.server 8000
# ブラウザで http://localhost:8000 を開く
```

## GitHub Pages 公開手順（暫定）

1. このディレクトリの内容を新規 GitHub リポジトリにpush（例: `nizukuri-tech/website`）
2. リポジトリ Settings > Pages で「Source: Deploy from a branch」「Branch: main」「Folder: /」を選択
3. https://nizukuri-tech.github.io/website/ で公開
4. カスタムドメイン `nizukuri-tech.com` を取得後、リポジトリに `CNAME` ファイルを追加し、ドメインのDNSをGitHub PagesのIPに向ける

## サイト構成（セクション）

1. ヒーロー — 「現役運送業 × AI × 中小最適化。3者を掛け合わせた、不在の存在。」
2. 課題（CHALLENGES）— 4つの典型的な困りごと
3. サービス（SERVICES）— IT相談・自動点呼・配車/出勤管理・セキュリティ・個別開発
4. 強み（WHY US）— 三位一体ポジショニング
5. 事例（CASES）— 親会社で稼働中の3システム
6. 想い（MESSAGE）— 代表メッセージ（事業計画.md §13 を編集）
7. 会社情報（COMPANY）— 会社概要
8. お問い合わせ（CONTACT）— メール・電話

## 初版で未完了の項目

- [ ] AI生成画像の作成・配置（`images/` 参照）
- [ ] 電話番号の差し替え（現状「準備中」）
- [ ] メールアドレス（`info@nizukuri-tech.com`）の実際の取得・運用設定
- [ ] OGP用のシェア画像（`og-image.png` 等）
- [ ] favicon
- [ ] アクセス解析（Google Analytics等）の判断

## 更新方針

- HTML/CSS が分かる範囲で直接編集できる構造（フレームワーク・ビルドツールなし）
- AI（Claude Code）に「サービス章のテキストを更新して」のような自然文で依頼可能
