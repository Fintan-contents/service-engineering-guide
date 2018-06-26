# サービス開発のエンジニアリングガイド

* [はじめに](#はじめに)
* [サービス開発の考え方](#サービス開発の考え方)
* [エンジニアを育成する](#エンジニアを育成する)
* [システムアーキテクチャを設計する](#システムアーキテクチャを設計する)
* [アプリケーションアーキテクチャを設計する](#アプリケーションアーキテクチャを設計する)
* [開発プロセスを設計する](#開発プロセスを設計する)
* [開発環境を準備する](#開発環境を準備する)
* [テスト環境と本番環境を用意する](#テスト環境と本番環境を用意する)
* [テストを計画する](#テストを計画する)
* [アプリケーションを実装・テストする](#アプリケーションを実装・テストする)
* [サービスをリリースする](#サービスをリリースする)
* [サービスを運用する](#サービスを運用する)

## はじめに

このドキュメントは、サービス開発のエンジニアリング部分を担うエンジニアに対して、開発開始前・開発中になにをすべきか、なにを参照すれば良いかを示すものです。サービス開発に必要と考えているアクティビティについて、現時点で最適と考えている進め方を記載しています。プロジェクトのメンバースキルや文化に強く依存するため、ここでは開発プロセスを定めていません。

サービスの開発開始前にこのドキュメントを一通り確認して、開発をどのように進めるか検討してください。検討にあたって不明な点や相談したい点などがあれば、協業などお力になれることがあると思いますので、[adc_support@pj.tis.co.jp](mailto:adc_support@pj.tis.co.jp)までご連絡ください。

TDD（テクノロジー開発部）では、[仮説検証サイクルの高速化に向けた取り組み](about.md)を進めており、現場で経験したノウハウや事例を積極的にコンテンツに取り込みたいと考えていますので、ご協力頂ける場合もTDDまでご連絡ください。

### このドキュメントの対象読者

サービス開発のエンジニアリング部分を始めようとしているエンジニアや、実際にサービス開発を進めているエンジニアを対象としています。

## サービス開発の考え方

サービス型ビジネスモデルにおいては、変化が速く不確実で予測困難な市場に対して、ビジネス面の仮説検証サイクルを繰り返し、市場の反応を見ながらサービスを改善して付加価値を高めていくことが重要になります。

このようなモデルでは、サービスの成功にはビジネス仮説の検証機会を増加させることが必要となりますが、そのためには、いかにしてビジネス仮説から市場へのローンチまでにかかる時間（リードタイム）を短縮するかが鍵になってきます。

> **仮説検証サイクル**
>
> ![development-flow](./images/development-flow.png)

## エンジニアを育成する

創造的なサービス開発において、開発チームは自己組織化されたチームであることが求められます。つまり、自分たちで、自分たちにとって最適のやり方を選択し、サービスの付加価値を高めていくことが求められます。

そのためには、サービス開発のチームを構成するとき、開発メンバーは機能横断的であり、チームとしてフルスタックのスキルをカバーするように構成するのが望ましいです。特に、個々のメンバーはT字型のスキルを持ち、継続的に必要なスキルセットを獲得していく必要があります。

サービスを開発するエンジニアの育成についてお困りの場合、[技術支援・Q&Aサービス『canal(カナル)』](http://canal.intra.tis.co.jp)で気軽に相談してください。研修の紹介や協業などご協力できると思います。

## システムアーキテクチャを設計する

まずは今から構築するサービスを俯瞰し、全体がどのように構成されるのかを設計・可視化することで、サービスのシステム的な側面についてチームの認識を合わせることができるようになります。

システムアーキテクチャの設計についてお困りの場合、[技術支援・Q&Aサービス『canal(カナル)』](http://canal.intra.tis.co.jp)で気軽に相談してください。

また、協業プロジェクトなどで実際に採用したシステムアーキテクチャの事例などを、今後拡充していきます。

## アプリケーションアーキテクチャを設計する

クラウドネイティブなアプリケーションアーキテクチャを採用することで、サービス開発のプラットフォームを利用してクラウドのメリットを十分に生かすことができます。

クラウドネイティブなアプリケーションアーキテクチャについては、次のリンク先を参照してください。

* [クラウドネイティブなアプリケーションの開発](application-development.md)

また、構築するアプリケーションの特徴に合わせて、利用するアプリケーションフレームワークも決定する必要があります。[Springアプリ開発ノウハウ集](https://ci.keel-dev.net/doc/crib-notes-build/branches/release-201806.9c841k/lastSuccessful/archive/doc/_build/html/index.html)では、広いエコシステムを持ち、クラウドサービスとの連携も充実している、Javaアプリケーションフレームワーク[Spring](https://spring.io/)についてのノウハウをまとめています。

* [Springアプリ開発ノウハウ集](https://ci.keel-dev.net/doc/crib-notes-build/branches/release-201806.9c841k/lastSuccessful/archive/doc/_build/html/index.html)

## 開発プロセスを設計する

サービスの開発では、市場に投入してフィードバックに基づいて改善する、というサイクルを頻繁に回していくことが重要です。

そのため、漸次的にアプリケーションを作り上げていくスクラムのような開発プロセスが好ましいです。

スクラムに関してはアプリケーション開発標準 - Fintanのスクラム関連のコンテンツを参照してください。

* [Fintan](http://adc.intra.tis.co.jp/wiki/Fintan)
  * スクラム概論
  * スプリント開始条件チェックリスト
  * スクラム開発プラクティス集

## 開発環境を準備する

サービスを開発するチームにとって、チケット管理（かんばん）やGitリポジトリ、チャットは必要不可欠なツールです。

アプリケーション開発標準 - FintanのNoPを使うことで、これらのツールが用意されたチーム開発環境を素早く作ることができます。

* [Fintan](http://adc.intra.tis.co.jp/wiki/Fintan)
  * [NoP](https://alfort.adc-tis.com/gitbucket/lapras/nablarch-on-paas)

## テスト環境と本番環境を用意する

TDDでは「エンジニアリングの高速化」を実現するため、サービスを開発するエンジニアがアプリケーション開発に集中できる環境を整備していきます。

そのために、クラウド上に開発環境やサービス実行・運用基盤を構築し、サービス開発のプラットフォームとして提供します。

プロジェクトはプラットフォームを利用することで、テスト環境・本番環境を構築する必要がなくなり、運用の負荷も軽減されます。

* [プラットフォーム提供のロードマップ](about.md#keel-roadmap)

## テストを計画する

アプリケーションに対して何をどこまでテストすればリリースできるのかを検討することは、リスクに見合わない過剰な投資を避けるなど、サービスのROIを高めることに役立ちます。また、リリースのための基準を設けることで、開発を進めやすくなる側面もあります。

そして、何をどこまでテストするかを決めたら、開発プロセスの中でいつどうやってテストしていくのかを計画します。そうすることで、アプリケーションの品質をどのように作りこむのか、見通すことができるようになります。

テストを計画するにあたっての詳細は、アプリケーション開発標準 - Fintanのテスト関連のコンテンツを参照してください。

* [Fintan](http://adc.intra.tis.co.jp/wiki/Fintan)
  * [全体テスト計画ガイド](https://alfort.adc-tis.com/gitbucket/Fintan/master-test-plan-standard/blob/master/README.md)
  * [テスト種別＆観点カタログ](https://alfort.adc-tis.com/gitbucket/Fintan/testing-viewpoint)

## アプリケーションを実装・テストする

サービス開発では継続的で頻繁な市場投入とフィードバックの獲得が重要とされるため、アプリケーションを頻繁にリリースする必要があります。

この際に、手動でのリグレッションテストは、往々にして以降の継続的なリリースにおいてボトルネックとなります。そのため、例えば重要な一部の機能だけはリグレッションテストを自動化して最低限の品質を担保し、リリースの頻度を下げないようにするなどの対応が必要になります。

テストの自動化に取り組みたいときなど、[技術支援・Q&Aサービス『canal(カナル)』](http://canal.intra.tis.co.jp)で気軽に相談してください。

また、協業プロジェクトなどでのテスト自動化の実践例を、今後拡充していきます。

テストだけでなく、実装についてもサービス開発などを通じて得られるノウハウを整理し、「ノウハウ集」に集約することでプロジェクトやグループ全体が活用しやすい情報にしていきます。現在は、以下のノウハウ集を公開しています。

* [Springアプリ開発ノウハウ集](https://ci.keel-dev.net/doc/crib-notes-build/branches/release-201806.9c841k/lastSuccessful/archive/doc/_build/html/index.html)

## サービスをリリースする

サービスをリリースするときには、安全で確実なリリースが求められますが、簡単に実現できることではありません。

[テスト環境と本番環境を用意する](#テスト環境と本番環境を用意する)で紹介したプラットフォームでは、サービスの安全で確実なリリースを支援するための仕組みを用意します。

## サービスを運用する

サービスを市場に投入した後は、例えばアクティブユーザー数や、ページビュー数などの指標値を利用して市場からのフィードバックを観測します。そういったフィードバックを受けて、次の改善の優先順位を判断することになるため、指標値を可視化していつでも確認できるようにすることが望ましいです。

そういったサービスの指標値を可視化しいつでも確認できるようにするために、[テスト環境と本番環境を用意する](#テスト環境と本番環境を用意する)で紹介したプラットフォームでは、指標値を簡単に確認できるようにする仕組みを提供します。

また、自分たちのサービスのシステムメトリクスやログに関しても、サービスで簡単に確認できるように、プラットフォームからインターフェースを提供します。
