## Testing

### アジャイルテストの4象限
https://qiita.com/mwakizaka/items/91b8f18c4750a92838c2
https://slide.meguro.ryuzee.com/slides/62

![](https://qiita-user-contents.imgix.net/https%3A%2F%2Fqiita-image-store.s3.amazonaws.com%2F0%2F114437%2F5dd02f09-c4db-7a9a-c949-7109c583e710.png?ixlib=rb-1.2.2&auto=format&gif-q=60&q=75&s=c8a5715a195259a141b761355c170157)

- [実践アジャイルテスト](https://www.amazon.co.jp/%E5%AE%9F%E8%B7%B5%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%83%86%E3%82%B9%E3%83%88-%E3%83%86%E3%82%B9%E3%82%BF%E3%83%BC%E3%81%A8%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%83%81%E3%83%BC%E3%83%A0%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E5%AE%9F%E8%B7%B5%E3%82%AC%E3%82%A4%E3%83%89-Architects-Archive%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%96%8B%E7%99%BA%E3%81%AE%E5%AE%9F%E8%B7%B5-Gregory/dp/4798119970)に書かれているアジャイル開発におけるテストの分類
- 4つに分類される
  - Q1
    - アジャイルチームを支援する技術面のテスト
  - Q2
    - アジャイルチームを支援するビジネス面のテスト
    - 顧客からのハイレベルな機能テスト、等
  - Q3
    - 製品を批評（評価）するビジネス面のテスト
  - Q4
    - 技術面のテストを使った製品の批評（評価）


### テストピラミッド
https://maku77.github.io/memo/test-pyramid.html
https://thinkit.co.jp/article/13346

![](https://maku77.github.io/memo/test-pyramid.png)

- Unit Test、Integration Test、UI Test、の3つについて理想的なバランスを示した図
- つまり
  - ROI は Unit Test が ROI が最も良く、UI Test がもっと悪い
  - なので、Unit Test をきちんとやるべき
- Google も以下の比率を推奨している
  - 10%：UI Test
  - 20%：Integration Test
  - 70%：Unit Test
  - ただし、Google では小規模/中規模/大規模テストという分類をしている
    - https://developer.android.com/training/testing/fundamentals.html#testing-pyramid 


### TDD

https://speakerdeck.com/twada/history-of-tdd-xpjug-2018-keynote

- `BDD` は `TDD` の系譜
- `TDD` は テスト手法 ではなく 開発手法
  - テストを中心としてインクリメンタル（テスト✕設計✕実装✕リファクタリング）に開発を行う手法
- `TDD` ≒ `テストファースト`
  - テストを先に書くことがTDDではない
  - テストを通すコードを書くことがTDDではない
  - テストを通す設計をすることがTDDではない



### プライベートメソッドのテスト
https://t-wada.hatenablog.jp/entry/should-we-test-private-methods

- プライベートメソッドのテストは書かない
- じゃあどうするの？
1. パブリックメソッド経由でテスト
   - どこかのパブリックから呼ばれているはず
2. 別クラスのパブリックメソッドにする
   - リファクタリングする＝設計が悪い
   - テストしたいプライベート＝実はプライベートにすべきではないのでは
3. プライベートじゃなくする
   - Java だったらパッケージプライベート（protected）にするとか
4. リフレクション使う
   - 最終手段
   - 壊れやすいテストになるので本当に必要なとこだけ

めも
- つまりブラックボックステスト前提


### 4 Phase Test
https://qiita.com/eKushida/items/dcf1c3dc65d9c729eaa2
http://xunitpatterns.com/Four%20Phase%20Test.html

- UnitTest を4つのフェーズに分けて書くこと
- 可読性がよくなる
1. Setup
   - 前処理
2. Exercise
   - 実行
3. Verify
   - 検証
4. TearDown
   - 後処理



### Tools

- [artillery](https://github.com/artilleryio/artillery)
  - Node 製の負荷試験クライアント
  - >  a modern load testing and functional testing toolkit

