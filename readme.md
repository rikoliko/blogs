# Notes for me  

## General

- hugo serverでプレビュー時のindex.mdに適用されているcssファイルはオンライン上の(https://llxyo.github.io/css/styles.css)になっている
- そのため、index.mdのcssの適用を確認するには、一度pushした後に確認するか、デベロッパーツールのソース下にあるcssを仮置きして確認する

## CSS

- cssはassetes/css/template-styles.cssがpublic/css/styles.cssとして出力される
- フォントはWebフォントで設定する、ユーザー環境によって上手く適用されないおそれがある

## Taxonomies

- taxonomies = [tagsやcategoriesなど], terms = [各tagsやcategoriesの文字列]  
- TaxonomyTermsPagesはtagやcategoryの一覧、TaxonomyListPagesはtag等ごとの記事一覧
- terms一覧はlayouts/tags, categories or series/terms.html > layouts/_default/terms.html > layouts/_default/list.htmlの順で参照し設定
- posts一覧/pagesはtaxonomy.html>list.htmlの順で参照される
- トップページはindex.html>home.html>list.htmlの順で参照し設定される
- categories一覧はlayouts/categories/terms.htmlで設定、同様にseriesも可能
- customized-taxonomiesのbrand,genre一覧はlayouts/_default/terms.htmlで設定
- terms一覧のレイアウトはcss[.patterns-list li + li]以下や[.tag-inline]でカスタマイズ
- 各postsのfront-matterのtermsにすると表示が崩れるので[""]を入れる
- termsなどの一覧が表示されない場合は、taxonomyやtermに関わる余計なファイルを設置されて一覧ページに適用されている

## Section

- /content以下の分類、記事は1つのsection(content以下のdirectory)にしか属せない

## OGP

- <head>の_internal/opengraph.html,_internal/twitter_cards.htmlで設定している  
- OGPの画像はconfig.tomlのparams/imagesで設定
- OGPで表示される説明文はconfigのhasCJKLanguage,summaryLengthで長さを設定
- params/titleでタイトルを設定
- descriptionは恐らく無意味

## Related Pages

- layouts/partials/related.htmlとconfig.toml内の[related]で設定

## Farsinized

- <'bdo lang="fa" dir="rtl">متن<`bpo>で右横書き化
- TitleはMarkdown Fileから右横書き化できないので、fa/index.htmlの、231行目の<'h1>Title</'h1>から248行目までを、<'bdo lang="fa" dir="rtl"><'/bpo>で囲む
