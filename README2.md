
# test_pages_2

{{ site.documents }}

リンクタグは相対pathなら問題無し

[doc/01](doc/01.md)


GitHub Pagesの条件

- 絶対pathが使いずらい
  - \`\{\{ site.baseurl \}\}\`をつける必要がある。
- \{\{  \}\}をエスケープする必要がある(もともとの仕様)

# 最初のページ

index.mdがあればそれを読み込みindex.htmlを生成する。
なければREADME.mdから生成する。
それもなかったら？
