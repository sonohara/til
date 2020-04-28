## Security

### DevSecOps

とは
> DevSecOpsとは、ITサービスを提供する上で必要不可欠なセキュリティ対策を組み込みつつ、アプリケーションの開発からデプロイ(デリバリー)までのライフサイクルを効率的、安定的にまわそうというもの

> DevSecOpsの目的は、安全なソフトウェアを頻繁にリリースすること

![img](https://pages.business-on-it.com/rs/277-TSU-614/images/2004-whats-devsecops-1.png)

ポイント

1. シフトレフト
   - 工程のより前段階で対処、もしくは対処のための仕組み
2. 自動化
   - セキュリティ対策を『できるだけ』自動的に組み込む
3. 共有
   - セキュリティインシデント等は関係者等で共有されなくてはなりません
4. トレーサビリティ
   - セキュリティインシデント発生時に何が起こったかを明らかにするために追跡可能な状態

ツール

- SCA
  - Software Composition Analysis
  - アプリが利用しているライブラリの脆弱性をチェックする
  - 例
    - OWASP Dependency-Check、Retire.js、Vuls
- SAST
  - Static Application Security Testing
  - 静的解析ツール
  - アプリケーションのソースコードを解析し、脆弱性が含まれていないかどうかチェックする
  - 例
    - SonarQube
- DADT
  - Dynamic Application Security Testing
  - 動的解析ツール
  - アプリケーションを実際に動かし、脆弱性が含まれていないかどうかチェックする
  - 例
    - OWASP ZAP、AppScan
- IAST
  - Interactive Application Security Testing
  - 動的解析ツールと静的解析ツールの長所を併せ持つツール
  - 基本的には、動的解析ツールと同じような特徴があります。しかし、実行環境を監視しながら動的検査を行うことで、脆弱性の検出時に問題のコードを特定することができます
  - 例
    - CONTRACT ASSESS、Seeker

適用例

SCA／SAST
![](https://cz-cdn.shoeisha.jp/static/images/article/11084/11084_03.png)

DAST
![](https://cz-cdn.shoeisha.jp/static/images/article/11084/11084_02.png)

参考
- https://www.business-on-it.com/2004-whats-devsecops/
- https://codezine.jp/article/detail/10661
- https://codezine.jp/article/detail/11084


### Cloud Security

https://www.slideshare.net/ssuser713746/2020413-232305830

- クラウドバイデフォルト
  - とは
    - > 各府省で政府情報システムを整備するにあたって、クラウドサービスの利用を第一候補として検討するという方針
    - https://project.nikkeibp.co.jp/jpgciof/atcl/19/00003/00002/
- Cloud Security Alliance
  - とは
    - クラウド・コンピューティングのセキュリティを確保するための米国の業界団体
    - 2009年4月に設立
    - メンバー
      - https://cloudsecurityalliance.org/membership/current/
      - Google、Microsoft、IBM、AWS、とかとか有名どころがたくさん
  - CSA Security Guiance
    - CSAが発表しているセキュリティガイドライン
    - https://cloudsecurityalliance.org/research/guidance/
    - 2020年4月時点の最新はV4
    - 日本語版は以下
      - http://www.cloudsecurityalliance.jp/guidance.html

