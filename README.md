# サービス開発のガイド

## サービス開発の考え方

サービス型ビジネスモデルにおいては、変化が速く不確実で予測困難な市場に対して、ビジネス面の仮説検証サイクルを繰り返し、市場の反応を見ながらサービスを改善して付加価値を高めていくことが重要になります。

> **仮説検証サイクル**
> 1. ビジネスチャンスに繋がる仮説を立てる
> 2. 仮説に基づき、サービスを改善・拡充して市場へローンチする
> 3. 市場の反応を見ながら仮説を検証する
> 4. （1に戻りサイクルを回す）
>
> ![仮説検証サイクル](./development-cycle.png)

ビジネスチャンスに繋がる仮説検証の機会を増やすためには仮説検証サイクルを速く回す必要があり、そのためには、エンジニアリングを高速化し、サービスを短期間に市場へローンチすることがポイントになります。

----------------------------

## サービス開発に対する施策

TDD では、上記の考え方に基づき、「エンジニアリングの高速化」に寄与する施策として以下のことを実行します。

* サービス開発／実行／運用プラットフォームの構築
* クラウド前提アプリケーション開発の推進

----------------------------

### サービス開発／実行／運用プラットフォームの構築

「エンジニアリングの高速化」を実現するため、サービス開発者がアプリケーション開発に集中できる環境を整備します。
サービス開発者がアプリケーション開発に集中することで、開発スコープをアプリケーション開発に極小化し、開発リードタイムを短縮します。また、サービスの付加価値に直結するのはアプリケーションであるため、サービスの付加価値向上にも寄与します。

サービス開発者がアプリケーション開発に集中できる環境として具体的には、クラウド上に開発環境やサービス実行・運用基盤を構築し、TIS におけるサービス開発のプラットフォームとして提供します。

----------------------------

### クラウド前提アプリケーション開発の推進

TIS におけるサービス開発として、プラットフォームとしてクラウド上に構築されたサービス実行・運用基盤のメリットを享受するため、従来までのアプリケーション開発ではなくクラウドネイティブなアプリケーション開発を前提とします。

TIS におけるサービス開発として前提とするアプリケーション開発については [こちら](./application-development.md) を参照してください。  

----------------------------

### プロジェクト協業

TDD では、プラットフォームを活用してサービスを開発する協業プロジェクトを募集しています。
クラウドネイティブなアプリケーション開発やアーキテクチャ設計等を支援します。

以下の連絡先に、ご連絡ください。  
adc_support@pj.tis.co.jp

----------------------------

## ロードマップ

サービス開発のプラットフォームの構築は PS2 と協業しており、10月から提供を開始する予定です。

その他、次のようなコンテンツの追加を計画しています。

* 2018/08末 テスト自動化（結合テスト）に関する実践例
* 2018/09末 テスト自動化（性能テスト）に関する実践例

今後、TDD内で実践していくサービス開発で作成するすべてのソースコード・ドキュメントについても事例として公開していきます。

また、ノウハウ集およびプロジェクト事例については、継続的に拡充していきます。

----------------------------

## リンク

* [【Fintan】サービス開発で採用されるスクラム開発について]() 
* [【NoP】開発環境について]()
* [【canal】技術支援・Q&Aサービス](http://canal.intra.tis.co.jp)
* [ノウハウ集](https://ci.keel-dev.net/doc/crib-notes-build/branches/develop/lastSuccessful/archive/doc/_build/html/index.html)
* プロジェクト事例（Comming soon）

----------------------------
## 問い合わせ先

サービス開発に係るTDDの施策については、以下の連絡先に問い合わせください。  
adc_support@pj.tis.co.jp