## Jamstack

https://jamstack.org/

### Jamstackとは
https://microcms.io/blog/what-is-jamstack/
https://employment.en-japan.com/engineerhub/entry/2019/12/10/103000

- Netlify創業者のMatt Biilmann氏が提唱した言葉
- 特徴
  1. Webサーバーに依存しないサーバーレスな構成である
  2. 事前にビルドされた静的なファイルからJavaScript経由でAPIをコールする
  3. 静的ファイルをCDNから配信している
- JAM
  - JavaScript
    - 任意のフロントエンドフレームワーク、ライブラリ、またはバニラJavaScript
  - API
  - Markup
    - マークアップのテンプレートはデプロイ時に事前ビルドされている
    - 自動ビルドさせるとGood
- Pros／Cons
  - Pros
    - パフォーマンスが良い
      - 事前ビルドしたファイルをCDN経由で配信すれば、最初の送信時間を限りなく短くできる
    - 高いセキュリティ
      - サーバー側の処理がマイクロサービスAPIとして抽象化されているため、攻撃の対象領域を減らすことができる
    - 安く、スケールしやすい
      - CDNが最適
  - Cons
    - ユーザーのログインが必要なWebアプリケーションには向かない
- 例
  - サーバレスなSPA
  - ヘッドレスCMS

CSR With Prerendering が JAMStack に該当

![](https://cdn-ak.f.st-hatena.com/images/fotolife/b/blog-media/20191128/20191128172433.png)

イメージ

![](https://cdn-ak.f.st-hatena.com/images/fotolife/b/blog-media/20191128/20191128172447.png)