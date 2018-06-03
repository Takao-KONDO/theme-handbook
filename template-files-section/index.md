#Template Files Section

#テンプレートファイルについて

We introduced template files earlier in the handbook.  This next section is going to break up the different template files through the post types that they display and provide a more in depth explanation of the purpose for these template files.  You’ll also get a handle on some practical use cases for the different template files.

テンプレートについては、このハンドブックの先の章で紹介しました。この章では、さまざまな種類のテンプレートファイルを投稿タイプごとに分けて扱い、各テンプレートファイルの目的について、より深い説明を提供します。また、さまざまなテンプレートファイルの実際の使用例について扱います。

You’ll start with post template files that deal with displaying the Post post type.  Then you’ll look at page template files that display the Page post type and drill down into specific page templates that WordPress has built in to its functionality.  Next you’ll learn about attachment template files which display the attachment post type.  You’ll also learn about how to display custom post types that are built by a plugin in the custom post type templates.  Lastly, you’ll touch on some partial and miscellaneous template files which are important to include but don’t necessarily display post types.

最初に post 投稿タイプの表示を扱う投稿テンプレートファイルから始めます。 次に、page 投稿タイプを表示する固定ページテンプレートファイルを見て、WordPress の機能に組み込まれた、より特定の固定ページ用のテンプレートについて細かく見ていきます。 次に、添付ファイルの投稿タイプを表示する添付ファイルテンプレートファイルについて学びます。 それからまた、プラグインによって作成されたカスタム投稿タイプを、どのようにカスタム投稿タイプのテンプレートに表示するのかついても学びます。 最後に、含めることが重要ではあるが必ずしも投稿タイプを表示するわけではない、幾つかの部分テンプレートファイルやその他のテンプレートファイルについて触れます。

Note:  It’s important to understand WordPress doesn’t really break down template files down into specific types of template files such as post template files or attachment template files. Especially since many template files, such as index.php or search.php can display many different post types. To help you reference specific template files this handbook is categorizing them based on the post types they can display.

Note: WordPress が実際にテンプレートファイルというものを、投稿用のテンプレートファイルや添付ファイル用のテンプレートファイルなど、特定の投稿タイプごとに切り分けているわけではないことを理解することは重要です。 特に index.php や search.php のような多くのテンプレートファイルは、多くの異なる投稿タイプを表示できるからです。 このハンドブックでは、探したいテンプレートファイルを参照できるように、表示できる投稿タイプに基づいてテンプレートを分類しています。
