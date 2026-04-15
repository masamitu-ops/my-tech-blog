---
title: 'Astroブログの構成と運用のまとめ'
description: '画像のパス指定や記事の追加方法についての備忘録です。'
pubDate: 'Apr 15 2026'
heroImage: '../../assets/blog-placeholder-3.jpg'
---

## Astroブログの基本構成

今回構築したブログの主要なファイル構成は以下の通りです。

- **`src/content/blog/`**: 記事（Markdown）を格納する場所
- **`public/`**: 画像やファビコンなどの静的ファイルを置く場所
- **`src/pages/index.astro`**: ホーム画面のレイアウト

## 画像表示のポイント

画像を表示させる際、パスの指定でハマりやすいポイントがあります。

- **画像の配置**: `public/` 直下に置く。
- **Markdownでの指定**: `heroImage: '/ファイル名.jpg'` と書く。
- **注意点**: `/public/` は含めず、`/` から書き始めるのが正解です。

## 記事の更新フロー

1. Codespacesで `.md` ファイルを作成・編集。
2. `git add / commit / push` を実行。
3. GitHub Actionsが自動でビルドし、S3へ同期される。