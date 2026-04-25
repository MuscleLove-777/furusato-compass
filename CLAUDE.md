# ふるさと納税コンパス - スケジュールエージェントガイド

毎日JST 09:37に起動し、ふるさと納税の最新情報を3記事生成します。

## 1日のタスク

1. **リサーチ**: WebSearchで以下から3トピック
   - 主要ポータル（楽天/さとふる/ふるなび/チョイス/au PAY/JRE MALL/東急/セゾン）のキャンペーン
   - 人気返礼品ランキング・ジャンル別おすすめ
   - 控除上限額・税制改正・ワンストップ特例
   - 季節別おすすめ（春は新茶/夏は果物/秋は新米/冬はカニ等）
   - 高還元率自治体の動向
2. **画像**: Unsplash無料 (`site:unsplash.com japanese food`, `gift box`, `seafood meat`等)、URL `https://images.unsplash.com/photo-XXX?w=1600&h=900&fit=crop`
3. **記事3本**: `articles/YYYY-MM-DD-<slug>.html`、1200-1800字、h2を2-3
4. **index.html更新**: blog-grid最新6件、stat-articles更新、blog-empty削除
5. **sitemap.xml更新**: 新3本追記
6. **IndexNow通知**: indexnow-key.txt → POST
7. **git push**: `[auto] Add daily articles YYYY-MM-DD`

## 執筆ルール
- 日本語、ファミリー目線で実用的に
- タイトル28-40字、還元率・自治体名・年を入れる
- 末尾に「控除上限額は所得・家族構成等で異なる、シミュレータ確認推奨」必須
- 「絶対お得」「100%還元」等の誇張NG
- 実在人物画像NG、Unsplashのみ
- フッターのMuscleLove広告+3部作リンクは全ページ必須

## 記事HTMLテンプレート

```html
<!DOCTYPE html><html lang="ja"><head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{{タイトル}} | ふるさと納税コンパス</title>
<meta name="description" content="{{150字以内}}">
<link rel="canonical" href="https://musclelove-777.github.io/furusato-compass/articles/{{slug}}.html">
<meta property="og:type" content="article"><meta property="og:title" content="{{タイトル}}">
<meta property="og:description" content="{{要約}}"><meta property="og:image" content="{{Unsplash}}">
<meta property="og:url" content="https://musclelove-777.github.io/furusato-compass/articles/{{slug}}.html">
<meta name="twitter:card" content="summary_large_image"><meta name="twitter:image" content="{{Unsplash}}">
<script type="application/ld+json">{"@context":"https://schema.org","@type":"Article","headline":"{{タイトル}}","image":"{{Unsplash}}","datePublished":"{{YYYY-MM-DD}}","author":{"@type":"Organization","name":"ふるさと納税コンパス"}}</script>
<link rel="stylesheet" href="../assets/style.css"></head><body>
<nav class="filter-nav"><a href="../index.html" class="filter-btn">← トップに戻る</a></nav>
<main class="article-body">
<img class="article-hero-img" src="{{Unsplash}}" alt="{{タイトル}}">
<p class="article-meta">📅 {{YYYY-MM-DD}} · 🏷️ {{カテゴリ}}</p>
<h1>{{タイトル}}</h1>
<p>{{リード}}</p>
<h2>{{見出し1}}</h2><p>{{本文}}</p>
<h2>{{見出し2}}</h2><p>{{本文}}</p>
<h2>まとめ</h2><p>{{結論+CTA}}</p>
<p style="color:#6b7280;font-size:0.8rem;margin-top:40px;">※ 控除上限額や控除条件は所得・家族構成・他の控除との併用により異なります。寄付前に各ポータルの公式シミュレータでご自身の上限額をご確認ください。</p>
<a href="../index.html" class="back-link">← 他の記事を見る</a>
</main>
<footer class="site-footer"><div class="footer-inner">
<div class="footer-promo"><p class="promo-label">― Powered by MuscleLove ―</p>
<div class="footer-links">
<a href="https://x.com/MuscleGirlLove7" target="_blank" rel="noopener">𝕏 @MuscleGirlLove7</a>
<a href="https://www.patreon.com/MuscleLove" target="_blank" rel="noopener">💪 Patreon</a>
<a href="https://musclelove-777.github.io/ai-fukugyo-compass/" target="_blank" rel="noopener">🧭 AI副業コンパス</a>
<a href="https://musclelove-777.github.io/ai-tenshoku-compass/" target="_blank" rel="noopener">🚀 AI転職コンパス</a>
<a href="https://musclelove-777.github.io/ai-money-compass/" target="_blank" rel="noopener">💰 AIマネー羅針盤</a>
</div></div>
<p class="copyright">© 2026 ふるさと納税コンパス</p></div></footer>
</body></html>
```

## 守ること
- 毎日3本、タイトル重複NG
- 控除上限の注意書き末尾必須
- pages.yml は変更しない
- フッター必須リンクは絶対残す
