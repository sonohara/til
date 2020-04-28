## 分析

### データレイクとデータウェアハウスの違い
https://jp.talend.com/resources/data-lake-vs-data-warehouse/

項目|データレイク|データウェアハウス
-|-|-
データ構造|生データ|加工済みデータ
データの目的|未確定|確定済
ユーザ|データサイエンティスト|ビジネス担当者

https://aws.amazon.com/jp/builders-flash/202003/what-is-datalake/

データウェアハウス
![](https://d1.awsstatic.com/Developer%20Marketing/jp/magazine/2020/img_what-is-datalake_02.b5b7156effa551048d5d4798d519c6998fdbd9c4.png)

- 複数のシステム (RDBMS) のデータを集め、統合的に分析を行うための保存場所（倉庫）
- RDBMS 単体では扱うのが困難なサイズ（TB、PB）のデータを分析するため
- 分析の目的にあわせて事前に加工して保存している
- 例
  - Apache Hadoop + Hive／Presto
  - Amazon Redshift

データレイク
![](https://d1.awsstatic.com/Developer%20Marketing/jp/magazine/2020/img_what-is-datalake_03.400ad1b2419e388b236ddc0db945808b7bd1dbae.png)

- データレイクは加工する「前」のデータを保存している
- データウェアハウスに投入して分析をするという方法も広く使われている
- 生データを保存した時点では、西京焼きにするといった目的を決めておく必要がない
  - →　必要に応じて色々なニーズに対応できる
- 多様な生データをそのまま保存でき、安価でサイズ上限にも余裕があるが求められる
- 例
  - Amazon S3
- ラムダアーキテクチャ
  - データをバッチで処理するのに加えて、発生したデータが次々と流れこんでくるような場合に (これをストリームデータといいます)、両者を組み合わせて処理するアーキテクチャ


![ラムダアーキテクチャ](https://d1.awsstatic.com/Developer%20Marketing/jp/magazine/2020/img_datalake_architecture_02.8a13dfa3e08cd8acc4919ff40277975bb591669e.png)

- ユースケース
![ユースケース](https://d1.awsstatic.com/Developer%20Marketing/jp/magazine/2020/img_datalake_architecture_04.fff2ea2526a052ac357e9cc984a223c9b4d3ac0b.png)