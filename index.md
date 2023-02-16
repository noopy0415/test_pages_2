
# test_pages_2

{{ site.documents }}

リンクタグは相対pathなら問題無し

[doc/01](doc/01.md)

GitHub Pagesの条件

- 絶対pathが使いずらい
  - _config.ymlにbaseurlを
  - \`\{\{ site.baseurl \}\}\`をつける必要がある。
- \{\{  \}\}をエスケープする必要がある(もともとの仕様)

# 最初のページ

index.mdがあればそれを読み込みindex.htmlを生成する。  
なければREADME.mdから生成する。  
それもなかったらindex.htmlは生成しない(他のページは生成する)

# サブジュールの静的サイトジェネレータ

行けるか？→なぜか出来ない

# サブツリーの静的サイトジェネレータ

summoduleではなくsubtreeなら？

行けるけど、操作が面倒

- 追加

    ```sh
    # git remote add -f リモート名 リポジトリ.git
    $ git remote add -f markdown-test https://github.com/noopy0415/markdown-test.git
    # git read-tree --prefix=フォルダパス -u リモート名/ブランチ名
    $ git read-tree --prefix=doc/markdown-test -u markdown-test/main
    ```

- 更新

    ```sh
    # git subtree pull --prefix=サブツリーフォルダ リモート名 ブランチ名
    $ git subtree pull --prefix=doc/markdown-test/ markdown-test main

    # git subtree push --prefix=サブツリーフォルダ リモート名 ブランチ名
    $ git subtree push --prefix=doc/markdown-test/ markdown-test main
    ```

    このコマンドが覚えれないので`.git/config`に書いておくと便利らしい

    
- 削除

    ```sh
    $ rm -rf 対象のフォルダ
    ```

