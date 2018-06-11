#Post Template Files

#投稿 (post 投稿タイプ) 用のテンプレートファイル

There are many template files that WordPress uses to display the Post post type. Any content dealing with a blog or its posts are within the Post post type.

WordPress が投稿 (post 投稿タイプ) を表示するために使用するテンプレートファイルはたくさんあります。ブログまたはその投稿を扱うコンテンツは、post 投稿タイプに含まれます。

##Index.php #Index.php

##index.php

index.php will display Post post types if there is no other template file in place. As stated in many places, every theme must have an index.php file to be valid. Many basic themes can get away with just using the index.php to display their Post post types, but the use cases given above would justify creating other template files.

index.php は、他のテンプレートファイルがない場合、post 投稿タイプを表示します。 多くの場所で述べられているように、すべてのテーマに、有効な index.php ファイルが必要です。 多くの基本テーマでは、post タイプを表示するために index.php だけが使用されうるのではありませんが、先に述べた使用ケースがあることで、他のテンプレートファイルを作成することが正当化されるでしょう。

Often you will want unique content structure or layout depending on what is being displayed. There are many templates you can use to customize content structure based on the context within the site. The two most notable post template files are home.php and single.php which display a feed of posts and a single post respectively.

表示される内容が何であるかに応じて、独自のコンテンツ構造やレイアウトが必要になることがよくあります。 サイト内のコンテキストに基づいてコンテンツ構造をカスタマイズするために使用できるテンプレートが、たくさんあります。 最も注目すべき投稿テンプレートファイルは home.php と single.php の2つで、それぞれ投稿のフィードと個別の投稿を表示します。

Top ↑

##Home.php #Home.php

##home.php

When a static front page is used and the site has a page defined for the blog list the home.php file is used for the designated blog list page. Use of this template is encouraged over creating a custom page template because blog pagination on a custom page template will not work properly. If there is no home.php in the theme index.php will be used instead.

フロントページとして静的なページが使用され、かつブログの一覧用に定義されたページがある場合、home.php ファイルが、指定されたブログ一覧ページに使用されます。 カスタムページテンプレートではブログのページングが正しく機能しないため、カスタムページテンプレートを作成するより、このテンプレートを使用することをお勧めします。 テーマに home.php がない場合、代わりに index.php が使用されます。

Top ↑

##Single.php #Single.php

##single.php

It’s good sense to build as simply as possible in your template structure and not make more templates unless you have real need for them. Therefore, most theme developers don’t create a single-post.php file because single.php is specific enough. For the most part, all themes should have a single.php. Below is an example of a single.php file from the theme Twenty Fifteen.

テンプレート構造をなるべく簡潔にし、本当に必要な分以上のテンプレートを作成しないのは良い考えです。ですので、ほとんどのテーマ開発者は、single.php が十分に特定的であるため、single-post.php ファイルを作成しません。 通例、すべてのテーマに single.php が必要です。 以下は、テーマ Twenty Fifteen の single.php ファイルの例です。


1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
<?php
/**
 * The template for displaying all single posts and attachments
 *
 * @package WordPress
 * @subpackage Twenty_Fifteen
 * @since Twenty Fifteen 1.0
 */
 
get_header(); ?>
 
    <div id="primary" class="content-area">
        <main id="main" class="site-main" role="main">
 
        <?php
        // Start the loop.
        while ( have_posts() ) : the_post();
 
            /*
             * Include the post format-specific template for the content. If you want to
             * use this in a child theme, then include a file called called content-___.php
             * (where ___ is the post format) and that will be used instead.
             */
            get_template_part( 'content', get_post_format() );
 
            // If comments are open or we have at least one comment, load up the comment template.
            if ( comments_open() || get_comments_number() ) :
                comments_template();
            endif;
 
            // Previous/next post navigation.
            the_post_navigation( array(
                'next_text' => '<span class="meta-nav" aria-hidden="true">' . __( 'Next', 'twentyfifteen' ) . '</span> ' .
                    '<span class="screen-reader-text">' . __( 'Next post:', 'twentyfifteen' ) . '</span> ' .
                    '<span class="post-title">%title</span>',
                'prev_text' => '<span class="meta-nav" aria-hidden="true">' . __( 'Previous', 'twentyfifteen' ) . '</span> ' .
                    '<span class="screen-reader-text">' . __( 'Previous post:', 'twentyfifteen' ) . '</span> ' .
                    '<span class="post-title">%title</span>',
            ) );
 
        // End the loop.
        endwhile;
        ?>
 
        </main><!-- .site-main -->
    </div><!-- .content-area -->
 
<?php get_footer(); ?>

In the code example above you can see the header is pulled in with get_header() then there are a two html tags. Next the Loop starts and the template tag get_template_part( 'content', get_post_format()); pulls in the appropriate content by determining the post type with get_post_format(). Next, comments are pulled in with the template tag comments_template(). Then there is some pagination. Lastly, the content divs are closed and then footer is pulled in with get_footer().

上のコード例では、ヘッダーが get_header() で読み込まれ、次に2つの HTML タグがあることが分かります。次にループが始まり、テンプレートタグ  get_template_part( 'content', get_post_format()); が、get_post_format() で投稿タイプを決定することにで、適切なコンテンツを取得します。その次に、テンプレートタグ comments_template() を使用して、コメントを取得します。その後、ページネーションがあります。最後に、コンテンツの div が閉じられてから、フッターが get_footer() で読み込まれます。

Top ↑

Singular.php #Singular.php
WordPress Version 4.3 added singular.php that comes in the hierarchy after single.php for posts, page.php for pages, and the variations of each. This template follows the rules of is_singular() and is used for a single post, regardless of post type. Themes that used the same code for both of those files (or included one in the other) can now simplify down to the one template.

WordPress のバージョン 4.3 では、singular.php が追加されましたが、これは、階層構造の中で、投稿 (post 投稿タイプ) では single.php の後に、固定ページでは page.php の後に来るものであり、それぞれのバリエーションです。このテンプレートは is_singular() の規則に従い、投稿タイプの種別にかかわらず単一の投稿に使用されます。 これらのファイルの両方に同じコードを使用したテーマ（または一方を他方にインクルードしたもの）は、今では1つのテンプレートに単純化できます。

Top ↑

##Archive.php #Archive.php

##archive.php

Unless a developer includes meta data with permalinks in their templates, the archive.php will not be used. Meta data is information tied to the post. For example the date something was posted on, the author, and any categories, tags, or taxonomies used for the post are all examples of meta data. When a visitor to a website clicks on the meta data, the archive.php will render any posts associated with that piece of meta data. For example, if a visitor clicks on the name of an author, the archive.php will display all posts by that author.

開発者がテンプレートに、パーマリンクを伴うメタデータを含めるのでない限り、archive.php は使われないでしょう。メタデータとは、投稿に結び付けられた情報です。たとえば、投稿された日付、投稿の作成者、投稿に使用されたカテゴリー、タグ、タクソノミーなどは、すべてメタデータの例です。ウェブサイトの訪問者がメタデータをクリックすると、archive.php はそのメタデータの一部に関連する投稿を表示します。たとえば、訪問者が作成者の名前をクリックすると、archive.php は、その著者によるすべての投稿を表示します。

Commonly, the title of the page being displayed by archive.php will be the name of the meta data the user clicked on. So if the user clicked on the Author’s name, the page name displaying all the other author’s posts will be the Author’s name and frequently there might be an additional description about the meta data. Here is a code example from Twenty Fifteen on their achive.php file. This snippet is the only piece of code that makes the archive.php file different from a home.php or index.php file.

一般に、archive.php によって表示されるページのタイトルは、ユーザーがクリックしたメタデータの名前になります。したがって、ユーザーが作成者の名前をクリックすると、当該作成者のその他のすべての投稿を表示するページ名として作成者の名前が表示され、そこにはしばしばメタデータに関する追加の説明がある可能性があります。 ここでは、achive.php ファイルの Twenty Fifteen のコード例を示します。このスニペットは、archive.php ファイルを home.php ファイルまたは index.php ファイルと異なるようにする唯一のコードです。

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
<header class="page-header">
    <?php
        the_archive_title( '
 
<h1 class="page-title">', '</h1>
 
 
' );
        the_archive_description( '
 
<div class="taxonomy-description">', '</div>
 
 
' );
    ?>
</header>
 
 
<!-- .page-header -->

Top ↑

##Author.php and Date.php #Author.php and Date.php

##author.php and date.php

Author.php and date.php are more specific archive type files. If you need a refresher check out where they fit within the template heirarchy. Generally, archive.php will suffice for most themes’ needs and you won’t need to create these templates.

author.php と date.php は、より特定的なアーカイブタイプのファイルです。そう述べる意図が分からない場合は、これらがテンプレート階層内のどこに収まるのか確認してください。一般的に、archive.php は、ほとんどのテーマのニーズに十分であり、これらのテンプレートを作成する必要はありません。


###Author.php #Author.php

###author.php

If you are building a theme designed for multiple authors, it might make sense to build an author.php template. In the author.php template you could provide more information about an author, their gravatar, pull in their social media sites, and then all posts written by them. This would be a step up from relying just on the archive.php file.

複数の投稿作成者のために設計されたテーマを構築する場合は、author.php テンプレートを作成することが理にかなっています。author.php テンプレートでは、作成者についてのより詳しい情報、グラバター（ gravatar ）、彼らのソーシャルメディアサイトを表示しつつ、彼らによって書かれたすべての投稿を提供することができます。これは archive.php ファイルだけによる場合と比べて一つの進歩でしょう。

Additionally, you can build specific author.php files for individual author’s by using their author ID or nicename. For example, say John Doe is the head author for a site with many guest authors. You may want all the guest authors’ information to display with author.php but you might build a specific author page with more information for John Doe by creating author-johndoe.php or author-3.php if his author ID is 3.

さらに、作成者IDまたはナイスネーム (nicename) を使用して、個々の作成者のための特定の author.php ファイルを作成することもできます。たとえば、John Doe 氏が多くのゲストの投稿作成者がいるサイトの最上位の作成者だとします。そこでもし、すべてのゲストの作成者の情報を author.php で表示したいものとすれば、それに対し John Doe 氏の詳細情報を含む特定の作成者ページを作成するには、author-johndoe.php を、または、作成者IDが3だとすれば author-3.php を作成すればよいことになります。

Top ↑

###Date.php #Date.php

###date.php

Similarly, if you are building a theme directed at magazine or news websites, a date.php file might make sense to build as these websites frequently organize their articles and posts by date or issue. Additionally, you could build a day.php, month.php, or year.php if you found enough justification for it.

同様に、雑誌やニュースのウェブサイト向けのテーマを構築している場合、これらのウェブサイトは、しばしば記事や投稿を日付や問題別に整理しますが、date.php は、その構築の際に理にかなっています。さらに、十分な正当性が確認された場合は、day.php、month.php、または year.php を作成することもできます。

Top ↑

##Category.php, Tag.php, and Taxonomy.php #Category.php, Tag.php, and Taxonomy.php

##category.php、 tag.php と taxonomy.php

If you need a refresher on what categories, tags, & taxonomies are you can look at their page. Often you won’t need to build out these template files. However, in an example of building a theme for food bloggers, there are some use cases for building these specific templates. In a food blogger website, the categories could be Great Restaurants, Beautiful Food, Ethnic Cuisine, and Recipes.

もし、カテゴリーやタグ、タクソノミーが何であるのか思い出したい場合は、それらのページを見ることができます。 しばしば、これらのテンプレートファイルを構築することは不必要です。しかしながら、フードブロガーのテーマを構築する例では、これらの特定的なテンプレートを構築するのに向いた使用ケースがいくつかあります。フードブロガーのウェブサイトでは、カテゴリーは、「素晴らしいレストラン」「美食」「エスニック料理」「レシピ」になりえます。

You might want most of your blog posts to display the same way except for any blogs that are categorized as recipes, because all recipes have ingredients and instrucitons sections. Therefore, you may want to build a category-recipe.php file to display your recipe blog posts in a grid view with some of the important details about the recipe visible.

ブログの投稿の大部分を同じ方法で表示したいのに、「レシピ」のカテゴリーのブログだけはそうはいかない、なぜならレシピはすべて食材と手順説明のセクションがあるから、ということがあるかもしれません。そこで、レシピのブログ記事をグリッド表示に並べ、各レシピの重要な詳細のいくつかをその中に表示するために、category-recipe.php ファイルを作成することができます。

Additionally, perhaps chocolate is a really important tag for the theme you’re building. It might make sense to build a tag-chocolate.php file so that you can display a specialized banner image of chocolate.

さらに、もしかすると「チョコレート」はあなたが構築しているテーマにとって本当に重要なタグかもしれません。その場合は、tag-chocolate.php ファイルを作成して、チョコレートの特別なバナー画像を表示できるようにするとよいかもしれません。

Top ↑

##Search.php #Search.php

##search.php

Most themes have a search.php file so it is clear to users that their query went through. It is common to have some sort of header identifying the query results such as this snippet found int twenty fifteen’s theme.

ほとんどのテーマには search.php ファイルがあり、そのお陰でユーザーにクエリーが完了したことが分かります。ヘッダーには、どんなクエリーの結果かを識別する、以下に示す Twenty Fifteen テーマ内のスニペットのような何かがあるのが一般的です。

1
2
3
4
5
6
7
8
9
10
<header class="page-header">
 
 
<h1 class="page-title"><?php printf( __( 'Search Results for: %s', 'twentyfifteen' ), get_search_query() ); ?></h1>
 
 
</header>
 
 
<!-- .page-header -->

This code snippet pulls in the query that was searched with get_search_query(). Often search.php will only pull in the excerpt instead of the full content since the user is trying to determine if the article or page fits their search.

このコードスニペットは、get_search_query() で検索されたクエリーを取得します。search.php では、ユーザーは記事やページが検索に合っているかどうかを判断しようとしているため、多くの場合、完全なコンテンツではなく抜粋のみを抽出します。

 
