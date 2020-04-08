## Golang

### テスト
#### Go の Test の考え方
https://qiita.com/Jxck_/items/8717a5982547cfa54ebc

go test には assert がない

- [Why does Go not have assertions?](http://golang.org/doc/faq#assertions)
- [アサート(assert)がない理由は? ](http://golang.jp/go_faq#assertions)

> Assert は便利だけど、頼り過ぎてエラーのレポートが適当になる。エラーレポート重要だからきちんと書こう。議論の余地はあるけど、新しい試みとしてやってみる

- [Where is my favorite helper function for testing?](http://golang.org/doc/faq#testing_framework)
- [テスト用のヘルパー関数がみあたりません](http://golang.jp/go_faq#testing_framework)

> みんなテストを書くためにすぐミニ言語作りたがるけど、必要な機能はだいたい Go 本体に揃ってるから、覚えること増やす必要無い。そうやって自動生成したエラーレポートより、ちゃんと自分で意図を書こう。面倒なのは分かるけど、そのコードに全く詳しくない人や、後のデバッグする時にそのコストは回収できるはず

Go標準パッケージでも地道に書いてる
「何が落ちたか」よりも、「なんで落ちたか」が書かれてる
→　書くのは面倒ですが、はじめてこのコードを見る人でも、きっと意味がわかる


#### interface を使ってモック化する
https://deeeet.com/writing/2016/10/25/go-interface-testing/

- interface を使って実装を差し替える（モックポイント）
- 外部とやりとりする部分をモックにする
  - DB
  - API

#### os.Exit をテストする
http://mattn.kaoriya.net/software/lang/go/20161025113154.htm




