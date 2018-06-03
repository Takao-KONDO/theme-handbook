# Theme Development Examples
# テーマ開発の例

One of the best ways to understand theme coding standards is to find examples of other themes that have been written with these standards in mind.  
テーマコーディング標準を理解する最良の方法の1つは、これらの標準を念頭に置いて作成された他のテーマの例を見つけることです。

## Default “Twenty” themes
## デフォルトテーマ "Twenty"

Packaged in every version of WordPress since version 3.0 (and named after the year they were released in), the default themes are some of the best to study how themes are built. This is because they are designed with broad use in mind and fully adhere to WordPress coding standards. You can download and study their theme files, and keep them around as examples to reference while learning how to develop your own themes:  
バージョン3.0以降のすべてのバージョンのWordPressに同梱されています（リリースされた年の後に名前が付けられています）。これらは幅広い使い方を念頭に置いて設計されており、WordPressのコーディング標準に準拠しているためテーマの構築方法を調べるのに最適です。テーマファイルをダウンロードしてテーマ開発の方法を学びながら参考にすることができます。

- [Twenty Seventeen](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentyseventeen)
- [Twenty Sixteen (only packaged in WordPress 4.8)](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentysixteen)
- [Twenty Fifteen](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentyfifteen)
- [Twenty Fourteen](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentyfourteen)
- [Twenty Thirteen](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentythirteen)
- [Twenty Twelve](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentytwelve)
- [Twenty Eleven](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentyeleven)
- [Twenty Ten](https://core.trac.wordpress.org/browser/trunk/src/wp-content/themes/twentyten)

## The Underscores theme
## Underscores theme
Unlike the default “Twenties” themes, the _s (or Underscores) theme is aimed at developers rather than end-users. It is intended to be a starter theme which you can use as a base to speed your development. It has a number of features:  
デフォルトの「Twenties」テーマとは異なり、_s（またはUnderscores）テーマはエンドユーザーではなく開発者を対象としています。 これは、開発のスピードを上げるための基礎として使用できるスターターテーマであることを意図しています。

下記のように多くの機能があります。

- Well-commented HTML5 templates, including error templates.  
よくコメントされたHTML5テンプレート（エラーテンプレートを含む）。
- A sample custom header implementation in inc/custom-header.php.  
inc/custom-header.phpのサンプルカスタムヘッダー実装。
- Custom template tags in inc/template-tags to keep templates organized and prevent code duplication.  
inc/template-tagsのカスタムテンプレートタグは、テンプレートを整理しコードの重複を防止します。
- A number of scripts to improve keyboard navigation—found in js/keyboard-image-navigation.js—as well as small screen navigation in js/navigation.js.  
js/navigation.js内の画面ナビゲーションだけではなく、js/keyboard-image-navigation.jsにあるキーボードナビゲーションを向上させるスクリプトも用意されています。
- Five sample CSS layouts in /layouts as well as starter CSS on which to build your design.  
/layoutsの5つのサンプルCSSと、ビルドするためのCSSスターター。
- GPL-licensed code.  
GPLライセンス規約

The features above make Underscores a great theme for a developer wanting to create their own theme. And even if you remove the extras, the base that’s left is a still an excellent example of a well-coded theme, developed with standards and best-practices in mind.
Underscoresは上記の機能により独自のテーマを作成したい開発者にとって大きなテーマになります。またエキストラを削除しても、残っているベースは標準とベストプラクティスを念頭に置いて開発された、きちんとコード化されたテーマの優れた例です。

A more detailed overview is available on Underscores’ website.
[Underscoresのウェブサイト](http://underscores.me/)でより詳細な概要をご覧いただけます。

Code for Underscores may be found at github.
[Underscoresのコードはgithubでご覧いただけます。](https://github.com/Automattic/_s/)

## Other Sources
## 他のソース

Additionally, all themes published in the theme directory are reviewed for standards prior to being published. Reviewing themes in the directory is a great way to better understand how theme development works and is a good way to get inspiration for your own theme.
テーマディレクトリに公開されている全てのテーマは、公開される前にコーディング標準に基づきレビューされます。テーマディレクトリ内のテーマを確認することは、テーマ開発の仕組みをよりよく理解するうえで非常に役立ち、自分のテーマ開発にインスピレーションを与える良い方法です。
