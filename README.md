# Jekyll

1. Jekyllをインストールします。

    * http://jekyllrb-ja.github.io/

    * コマンドプロンプトで実行：

    ```txt
    .\cmd.bat

    gem install jekyll
    ```

1. Jekyllの新規プロジェクトを作成します。

    * コマンドプロンプトで実行：

    ```txt
    .\cmd.bat

    jekyll new site

        # Running bundle install in C:/path/to/jekyll/site...
        #
        #     ...
        #
        # New jekyll site installed in C:/path/to/jekyll/site.
    ```

    ```diff
      ./jekyll
        + rubyinstaller-3.3.3-1-x64/
    +   + site/
    +     + _posts/
    +     + ...
        + .gitignore
        + cmd.bat
    ```

    * Jekyllが依存するGemが古い問題（後述のbundle installでエラーになる）の修正： site/Gemfile

    ```diff
      # Performance-booster for watching directories on Windows
    - gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]
    + gem "wdm", "~> 0.2.0", :platforms => [:mingw, :x64_mingw, :mswin]
    ```

1. Jekyllのサーバを起動します。（開発用）

    * コマンドプロンプトで実行：

    ```txt
    .\cmd.bat

    cd site

    bundle install
    bundle exec jekyll serve --trace

        # Configuration file: C:/path/to/jekyll/site/_config.yml
        #             Source: C:/path/to/jekyll/site
        #        Destination: C:/path/to/jekyll/site/_site
        #  Incremental build: disabled. Enable with --incremental
        #       Generating...
        #        Jekyll Feed: Generating feed for posts
        #
        # ...
        #
        #  Auto-regeneration: enabled for 'C:/path/to/jekyll/site'
        #     Server address: http://127.0.0.1:4000/
        #   Server running... press ctrl-c to stop.
    ```
