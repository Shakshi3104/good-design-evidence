---
title: Evidence - 🏆 グッドデザインデータ可視化ツール賞 2024 
---

---

# はじめに

この記事ではEvidenceというBIツールのデザイン的に優れているなぁと思うところを紹介していきます。
勝手にグッドデザインデータ可視化ツール賞 2024を授与します🎉 おめでとう〜🎉 (JDPによる[GOOD DESIGN AWARD](https://www.g-mark.org/)とは何の関係もありません)

この記事も[「Evidence使ってみた」をEvidenceで書いてみた](https://advent-calendar-evidence.evidence.app)と同じようにEvidenceで書いてみました。


## この記事で紹介する内容

EvidenceのUIデザインやユーザー体験の観点で優れているところを実例を交えて紹介します。

サンプルで使用するデータは嵐のCD・DVDの売上枚数のデータです (手打ちで作りました)。

<Details title="使用するデータ">

```sql arashi_sales_sample
select
  *

from arashi_sales.all_releases
```
<DataTable data={arashi_sales_sample} />

</Details>

ちなみに、このデータ+αを使って嵐のダッシュボードも作ってます: [ARASHI Songs](https://shakshi-arashi-songs.evidence.app)

特徴や使い方は、[「Evidence使ってみた」をEvidenceで書いてみた](https://advent-calendar-evidence.evidence.app)や下記の記事を読んでみてください。

- [コード管理できるBIツール「Evidence」の紹介](https://stable.co.jp/blog/introduction-evidence)
- [SQL+Markdownだけでデータ可視化できるOSS Evidenceを使ってPerfumeの楽曲分析をしてみる](https://qiita.com/yam_dr/items/c6d73c0694e68e8b8223)
- [evidenceを使用したデータの可視化](https://zenn.dev/rehabforjapan/articles/evidence-visualize)
- [🦐🦐🦐Markdownで書くBIツール、Evidence触ってみた🦐🦐🦐](https://zenn.dev/notrogue/articles/30367d2c302bd3)

---

# 受賞理由

グッドデザインデータ可視化ツール賞の受賞理由として、デザイン的に優れているところを3つ紹介します。

## 優れたUIを目指している
特に評価しているところは、Evidenceがコンセプトとして優れたUIを目指しているところです。

公式ドキュメントの[Motivation](https://docs.evidence.dev/motivation)ページには、「Our mission is to give you the tools to deliver production-quality data products that look and feel more like the New York Times' data journalism than a drag-and-drop dashboard. (私たちの使命は、ドラッグアンドドロップダッシュボードよりも**New York Timesのデータジャーナリズムのような外観と感触の品質のデータ製品を届けるためのツールを提供すること**です。)」と明記してあります。

実際に、[New York TimesのGraphics](https://www.nytimes.com/spotlight/graphics)を見てみると、なんとなくEvidenceと似てる気がします。[A Nation of Homebodies](https://www.nytimes.com/2024/10/05/upshot/americans-homebodies-alone-census.html)にある棒グラフとかEvidenceっぽいです。

**New York Timesの棒グラフ by [A Nation of Homebodies](https://www.nytimes.com/2024/10/05/upshot/americans-homebodies-alone-census.html)**
![bar_chart_nyt](https://static01.nytimes.com/newsgraphics/2024-09-25-time-use-home/1428503b-8964-44d5-b260-979e79e5b15a/_assets/charts-bar_chart-600.png)

**Evidenceの棒グラフ**

```sql arashi_sales_year
select
  strftime(リリース日, '%Y') as release_year,
  SUM(売上枚数) as sales_counts

from arashi_sales.all_releases
group by strftime(リリース日, '%Y')
```

<BarChart data={arashi_sales_year} sort=false />


## UIコンポーネントが多い

## レスポンシブルなUI
