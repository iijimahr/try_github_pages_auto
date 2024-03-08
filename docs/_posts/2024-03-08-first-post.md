---
layout: post
title: "Github Pagesで簡易ブログを作成"
---

## 手順

1. publicリポジトリの作成(無料ユーザだとpublicにしないと使えない様子)
2. repoのrootに`docs/index.md`を作成
3. Setting->Pages:
   1. Source: Deploy from a branch
   2. Branch: `main`, `/docs`
4. Actions: `pages build and deployment`なら成功
5. URL: <https://iijimahr.github.io/try_github_pages_auto/>

## 利用方針

- ブログ: blogというリポジトリを作ってrepo rootを公開
- プロジェクトページ: docsディレクトリをpublic rootとして公開

## テーマの設定

- Github Pagesは静的サイトジェネレータJekyllを利用。
- `_config.yml`をpublic rootに設置するとテーマを作ってくれる。

```yml:_config.yml
theme: jekyll-theme-caryman
```

- サポートされているテーマの一覧: <https://pages.github.com/themes/>
- 個人的に好きなテーマ
  - architect: 好き嫌いはありそうだが好き
  - cayman: よく見る
  - hacker: よく見る
  - minima: シンプルで好き

## Jekyll Front Matter

- Jekyllへ個々のファイル処理時の設定を伝える
- 公開するMarkdownファイルの先頭に以下のような記述を追記
- グローバル変数、ユーザ設定変数、ポスト(後述)の定義済み変数を参照することも可能

```yml
---
layout: post
title: Blogging Like a Hacker
---
```

## Jekyll Posts

- Posts: <http://jekyllrb-ja.github.io/docs/posts/>
- ブログの自動生成

## Jekyll Minima

- <https://github.com/jekyll/minima/>
- Jekyllでブログを作る時に便利なテーマ
- Layouts:
  - base: 基底フォーマット
  - home: トップページのみ
  - page: Aboutなど
  - post: ブログの各ポスト
- メタ情報:
  - category: ブログのカテゴリ(ディレクトリ分けと同等)
  - tags: ブログのタグ(複数設定可能; YAML list or スペース区切り)

## その他

- htmlだけでなくもととなるMarkdownファイルも見える
- カスタム Github Actions での公開は beta らしい
- 数式はMathJaxをいちいち呼ぶ感じか

## 参考

- GitHub Pages概要: <https://qiita.com/MahoTakara/items/3800e9dc83b530d0a050>
- GitHub Pages公式: <https://docs.github.com/ja/pages>
- Jekyll: <http://jekyllrb-ja.github.io/docs/>
- MathJax: <https://www.mathjax.org/>
