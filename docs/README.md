# 職務経歴書

## 基本情報

|key|value|
|---|---|
|氏名|砂土居 裕太（Sunadoi Yuta）|
|生年月日|1990/07/02|
|居住地|和歌山県|
|最終学歴|北海道大学大学院薬学研究院|
|blog|https://www.sunapro.com/|

---

## 技術スタック

### 言語
<p>
  <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" />
  <img alt="JavaScript" src="https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=JavaScript&logoColor=white" />
  <img alt="Go" src="https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=Go&logoColor=white" />
</p>

### フレームワーク・その他
<p>
  <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" />
  <img alt="Next.js" src="https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=Next.js&logoColor=white" />
  <img alt="Redux" src="https://img.shields.io/badge/-Redux-45b8d8?style=flat-square&logo=redux&logoColor=white" />
  <img alt="Storybook" src="https://img.shields.io/badge/-Storybook-FF4785?style=flat-square&logo=storybook&logoColor=white" />
  <img alt="Vite" src="https://img.shields.io/badge/-Vite-646CFF?style=flat-square&logo=Vite&logoColor=white" />
  <img alt="Apollo" src="https://img.shields.io/badge/-Apollo-311C87?style=flat-square&logo=apollo-graphql&logoColor=white" />
  <img alt="GraphQL" src="https://img.shields.io/badge/-GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white" />
  <img alt="MySQL" src="https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white" />
  <img alt="Docker" src="https://img.shields.io/badge/-Docker-46a2f1?style=flat-square&logo=docker&logoColor=white" />
  <img alt="GitHub Ations" src="https://img.shields.io/badge/-GitHub Actions-2088FF?style=flat-square&logo=GitHub Actions&logoColor=white" />
  <img alt="Serverless" src="https://img.shields.io/badge/-Serverless Framework-FD5750?style=flat-square&logo=Serverless&logoColor=white" />
  <img alt="Terraform" src="https://img.shields.io/badge/-Terraform-7B42BC?style=flat-square&logo=Terraform&logoColor=white" />
  <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />
  <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" />
</p>

---

## 目次
- 職務経歴書詳細
  - 株式会社TERASS
    - 開発環境の整備
    - Firebase emulatorsによるローカル環境の構築とテストの実装
    - 既存プロダクトの新機能開発
    - 検索機能の実装
  - 株式会社ストランザ
    - PHP → Goへのリプレイス
    - Reactによる検索画面の追加
    - マイクロサービスにおける認証機構の構築
  - 副業
    - RailsからGoへのリプレイス
    - 名簿アプリの作成
    - Three.jsを用いた3Dアニメーションの描画
- 業務外活動
  - 技術ブログ
  - 技術ブログの作成
  - OSS貢献
- 資格・業績

## 職務経歴詳細

### 株式会社TERASS (2021/05 ~ 現在)
#### 開発環境の整備

|key|value|
|---|---|
|プロジェクト規模|1人|
|役割|設計 / コーディング / 運用・保守|
|使用技術| <img alt="GitHub Ations" src="https://img.shields.io/badge/-GitHub Actions-2088FF?style=flat-square&logo=GitHub Actions&logoColor=white" /> <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" /> <img alt="Storybook" src="https://img.shields.io/badge/-Storybook-FF4785?style=flat-square&logo=storybook&logoColor=white" /> <img alt="Vite" src="https://img.shields.io/badge/-Vite-646CFF?style=flat-square&logo=Vite&logoColor=white" /> <img alt="Renovate" src="https://img.shields.io/badge/-Renvate-1A1F6C?style=flat-square&logo=Renovatebot&logoColor=white" />|

担当タスク以外にもやりたいことがあって認められればできるという環境だったので、いくつかの提案をして実行しました。具体的には次のことをやりました。

- Firebase preview channelの設定
- storybookのデプロイ環境の構築
- webpackからviteへのリプレイス
- Renovateの導入
- Vitestの導入

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### Firebase preview channelの設定
機能を実装したときにGit操作ができないPdMに仕様を画面上で確認してもらいたい、細かいUI上の修正を簡単に画面上で確認したいということが度々ありました。  
これを解決するために、PR作成時にそのPR内容を反映したものを一時的にデプロイしてくれるようなサービスがないかと考えました。AWS Amplifyではそういう機能があったのでFirebaseにも似たような機能がないか探したところ、Firebase preview channelというものがありました。  
GitHub ActionsでPRにpushした際、最新のPRの内容を反映したものをデプロイするよう設定し、PRを閉じたときに削除するよう設定しました。  
これによってPRで発行されたURLをクリックするだけでPR内容を確認できる環境ができ、開発体験が向上したと思っています。  
こちらの内容はブログにまとめました。  
https://www.sunapro.com/github-actions-firebase-preview/

### storybookのデプロイ環境の構築
storybookを使用しているものの、localにしか環境が存在しなかったためlocalでわざわざ立ち上げなくても最新の内容を確認できる環境が欲しかったので用意することにしました。  
FIrebaseのHostingを使ってstorybook用のホスティングを用意することを最初考えたのですが、チーム内でしか見られないprivateのものにしたいという要件があったため、認証周りの設定が複雑になりそうでした。  
調査した結果、chromaticというサービスを見つけこれであればGitHub Actionsを使ってマージ時に自動でデプロイできるようになるだけでなく、スナップショットを用いたビジュアルリグレッションテストによって意図しないスタイリングの崩れも検知できる仕組みを整えることができました。  
実際その後のQA作業でリリース前に意図しないスタイリングの崩れを検知できました。

### webpackからviteへのリプレイス
localでのサーバーの立ち上げがとても遅く毎回1分近くかかるという課題がありました。調べてみるとViteというビルドツールがあることを知りました。  
これは外部ライブラリにesbuildを使った高速なバンドル、ソースコードはバンドルをしないでES Modulesをそのまま読み込むのでとても速いというものだったので、ちょうど要件にあっていると思いこちらへのリプレイスを行いました。  
結果的に1分近くかかっていたサーバーの立ち上げが3秒程度になったので非常に快適な開発環境が整ったと思っています。  
こちらの内容はブログにまとめました。  
https://www.sunapro.com/webpack-to-vite/

### Renovateの導入
プロジェクトで使用しているライブラリでバージョンの古いものがいくつかあり、機能開発する上でそれが原因でバグが生じることが何度かありました。こういった背景からライブラリの定期的なアップデートをしたいということになり、どういった技術があるのか調査しました。  
DependabotやRenovateなどが代表的なツールであり、これらは定期的にライブラリのアップデートを監視してくれてPRを作成してくれますが、設定の細かさやPRの情報のリッチさなどからRenovateを採用することにしました。  
これによりライブラリが新しい状態を保つことができるようになっただけでなく、ライブラリの変更をきちんと追いかけるようになったのは良い副産物でした。  
こちらの内容はブログにまとめました。  
https://www.sunapro.com/renovate/  
運用方法の決め方や実際に半年間運用した振り返りをzennにまとめました。  
https://zenn.dev/sunadoi/articles/889219ab865583  
また、ライブラリのアップデートによってテストが落ちたことがあり、ライブラリ側のデグレーションらしき挙動だったのでissueを立てて修正してもらいました。  
ref: https://github.com/Hypercontext/linkifyjs/issues/351

### Vitestの導入
firestoreのrulesをテストする際にjestを使用していたのですが、watchモードでの変更の反映に20秒程度かかるという課題がありました。非常に開発効率が悪かったため高速で動作するテスティングライブラリであるvitestを使用することにしました。結果、watchモードでの変更の反映が1秒程度となり開発効率が非常に向上しました。  
結果的にテストを書くモチベーションも上がり、非常に良い開発体験を得られたと思っています。

</div>
</details>

#### Firebase emulatorsによるローカル環境の構築とテストの実装

|key|value|
|---|---|
|プロジェクト規模|1人|
|役割|要件定義 / 設計 / コーディング / テスト / 保守・運用
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Vitest" src="https://img.shields.io/badge/-Vitest-739B1B?style=flat-square&logo=Vitest&logoColor=white" /> <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" />|

当時、プロジェクトにローカル環境が整備されておらず、ローカルで動作確認をするためにもstaging環境のFirebaseに接続しなければならないという状況でした。

開発者の人数が少ないこともあってなんとか開発できてはいましたが、作業内容が被ると意図しない挙動になってしまったり、動作確認するために毎回デプロイが必要になったりと開発効率に課題を抱えていました。

この課題を解決するために、Firebaseのemulatorsを使用してローカル環境を構築しました。  
さらに、構築したemulators環境を利用してそれまでほとんど書かれていなかったテストを実装しました。

以下に詳細を記述します。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### emulators環境の構築
emulatorsのhosting機能は使用せず、firestoreやauthをemulators環境で立ち上げ、フロントエンドはviteで起動させた状態でemulatorsに接続する設計にすることで、快適な動作環境を構築できました。  
なお、emulatorsの起動とviteサーバーの起動、接続を1つのコマンドで行うためにProcfileを使用しています。

emulatorsのfirestoreやauthデータはファイルに永続化するようにしました。  
外部サービスとしてalgoliaを使っているため、algolia内のデータとemulatorsのfirestoreデータが一致しないという問題が生じましたが、emulatorsでのみ使用するalgolia環境を用意し、環境変数によって接続先を切り替えることで対応しました。

### テストの実装
既存のコンポーネントや関数はfirestoreとの結合度が高かったため、それまでテストが十分に行われていませんでしたが、emulatorsを導入したことでテストできる環境が整いました。  

テストを行うにあたって、まずテスト戦略をチームで話し合いました。  
結果として、以下のような戦略でテストを実装することになりました。

- ロジックのユニットテストは網羅的に行う
- コンポーネントのユニットテストは行わず、Chromaticを用いたスナップショットテストに一任する
- 複数コンポーネントを組み合わせたintegration testは必要な場面で行う
- E2Eテストは人による動作確認が大変な場面に絞って行う

実際にテストを書いていく中で変更はある前提ですが、ひとまず上記のように設定しました。  
まずはロジックのユニットテストを導入しました。  

ほとんどの関数がfirestoreへ接続するため、これをemulators環境に接続して行うようにしました。  
ここで考えなければならないのが、createやupdateしたデータがテスト間で影響し合わないようにする方法でした。  
ベストな方法はテスト環境ごとにemulators環境を別々で用意して、それぞれ接続するようにすることです。  
環境を隔離することで他のテストへの影響をなくせる上に、並列でテストを実行できるためテスト実行時間の短縮も望めます。

ただし、これはemulatorsの環境を別で用意する分だけportを確保する必要がありそれぞれのテストで別々のportに接続する必要があるため実装が非常に複雑になりそうでした。  
したがって、各テストは直列で実行しそれぞれのテストごとにfirestoreやauthのデータをリセットする方針としました。  
数十のテストを書きましたが全く問題なく書けており、vitestのおかげか当初心配していた実行時間の長期化も全く気になっていません。

実装の詳細はブログに記述しました。  
https://www.sunapro.com/vitest-firebase-emulators/

</div>
</details>

#### 既存プロダクトの新機能開発

|key|value|
|---|---|
|プロジェクト規模|1人|
|役割|要件定義 / 設計 / コーディング / テスト / 保守・運用
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" />|

**5ヶ月かかる大型の新規機能開発の実装を一人で任せていただき、4ヶ月でほぼ実装が完了しました。**

既存の機能はReduxを使用していましたが、チームとしてReduxへの依存はできるだけ減らすような方針なので、既存の実装方法を模倣せずにデータのやり取りは直接Firestoreとのみ行うこと、それに応じてキャッシュ化などを適切に行うことを意識して機能開発を行いました。

リリース後も修正に時間がかかるような大きな不具合はなかったです。

以下、苦労した点やバリューを発揮した点、気をつけている点などを記載します。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### 設計
カスタマーの登録ステータスや売却物件の情報など扱うべきデータ量がいくつか増えることになったので、それらをFirestore上でどう設計するかにとても悩みました。  
Firestoreでちゃんと設計するのは初めてでしたが、本を何冊か読むと読み取りコストや更新コスト、更新時のリアルタイム性を考慮した上で設計することが重要であると分かり、実際に開発する機能の特性を踏まえて読み取りコストを抑えるよう設計しました。  
これまでプロジェクトで使用したことのなかったコレクショングループなどの機能も使うことを踏まえて設計しました。  
設計をする上で注意すべきポイントやそれぞれの設計のメリットデメリットをある程度把握できたと思っています。

### 型安全性
React, TypeScriptを使った開発をしていますが、型安全性はかなり気を使っています。anyは一切使わず、型アサーションも極力使わないようにしています。  
その時の開発で問題なかったとしても、後々の改修などで意図しないコードになる可能性があることも考慮して、そういった場合に検知できるような型を定義することも心がけています。  
その一例をブログにまとめました。  
https://www.sunapro.com/tuple-type-check/

### 実装順序
数ある機能の中で、どの順番でタスクに取り掛かっていくべきかなども全て自分で決めました。  
デザインや仕様は確定していない部分も多い中で、それらがなくても進められる方法やどの順番で実装していくとスムーズかなどを常に考えて開発を進めました。仮置きして後で修正する部分のタスクの管理などもPdMやデザイナーと共有しながら進めており、取りこぼしのないようにしています。また、確定していない仕様やデザインに関しても積極的にこうした方がいいのではないかと議論を交わすように心がけています。

### 見積もり
確定している要素が少ない中で見積もりを出すのは非常に難しかったですが、それぞれの機能を細かくタスクに分解して整理して見積もりを出しました。  
実装途中で想定していなかった要素なども多々出てきましたが、それを見越して余裕を持ったスケジュールにしていたこともあり、現在スケジュール通り進められています。

### コミュニケーション
定期的に進捗を共有したり、スケジュールが遅れる可能性のある懸念点などもわかった段階で伝えるようにしています。  
日頃からこれらを意識しているおかげで、「仕事が早い、情報共有するタイミングが良い、スムーズなコミュニケーションが取れる」といったフィードバックをいただくことができました。

また、いいものを作りたいという思いが強いので、プロダクトのあるべき姿を考えた上でたとえ工数が増えるようなものであっても積極的に提案するよう心がけており、特に実装中にUI/UXが悪いと感じたものに関しては改善案を出しながら実装しています。

</div>
</details>

#### 検索機能の実装

|key|value|
|---|---|
|プロジェクト規模|1人|
|役割|要件定義 / 設計 / コーディング / テスト / 保守・運用
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" /> <img alt="algolia" src="https://img.shields.io/badge/-Algolia-5468FF?style=flat-square&logo=Algolia&logoColor=white" />|

検索機能に関連する以下の機能をalgoliaを使って実装しました。
- ユーザーの検索機能の実装
- 検索条件のお気に入り保存
- 保存したお気に入り条件に該当するユーザーが登録された際の通知機能

以下、実装時に気をつけたことや苦労したことなどを記載します。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### 型安全性
algoliaが提供しているコンポーネントライブラリを使用したのですが、検索する項目名がstringになっていたのでタイポしても気づけないという課題がありました。  
型安全性をもう少し高めた上で実装したいなと思い、template literal typesを使用して型安全性を高めました。  
こちらの内容はブログにまとめました。  
https://www.sunapro.com/library-template-literal-types/

### ライブラリ提供コンポーネントの機能不足
ライブラリで提供されている検索機能はコンポーネントに結びついているものであるため、ロジック部分だけを再利用するということができないものでした。ロジックのみを再利用したい場合は、display: noneを適用した親コンポーネントでラップして対応しました。  
また、SP対応ではモーダルで検索機能を実装しましたが、検索クエリの実装がコンポーネントに紐づいているため、モーダルを閉じた時にアンマウントされた影響で検索が意図しない挙動になるなどの不具合が生じました。こちらもモーダルを閉じる時にはアンマウントしないようにdisplay: noneを適用した親コンポーネントでラップしたものをマウントするようにして対応しましたが、コンポーネントとロジックが密結合になっていることの弊害を実感しました。

### 時間関連の検索条件
保存したお気に入り検索条件に該当するユーザーが登録された時に通知する機能では、ユーザーの条件と保存されている検索条件を比較する必要がありました。  
条件の中には「xxまで1週間以内」などの時間に関するものがあり、検索時にはタイムスタンプを使用していますが、タイムスタンプを保存すると時間と共に条件が適用しなくなってしまうという課題がありました。したがって、保存する検索条件としては"1週間以内"などのstringとし、通知時にタイムスタンプへ変換してどの検索条件がその時点でのユーザーの情報と適合するかを突合するようにして対応しました。  
この時、通知のタイミングでタイムスタンプに変換する処理で一部バグを生み出してしまったので、その原因と修正方法をブログにまとめました。  
https://www.sunapro.com/object-init/


</div>
</details>

### 株式会社ストランザ (2020/04 ~ 2021/04)
#### PHP → Goへのリプレイス

|key|value|
|---|---|
|プロジェクト規模|3人|
|役割| 設計 / コーディング / テスト / 保守・運用
|使用技術| <img alt="Go" src="https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=Go&logoColor=white" /> <img alt="MySQL" src="https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white" /> <img alt="Docker" src="https://img.shields.io/badge/-Docker-46a2f1?style=flat-square&logo=docker&logoColor=white" /> <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />|

PHPで動いている既存のアプリのバックエンドをGoのAPIとして切り出すリプレイスを行いました。
Goではクリーンアーキテクチャを意識して実装をしていました。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### 実装した内容
リプレイス後の挙動は同じでありがならも、パフォーマンスやDB負荷を下げられる部分は対応するという方針だったため、SQL部分は同じ結果となるようにしながらもパフォーマンスをあげられるような工夫が必要でした。  
具体的には実行計画をとってindexが効いていないSQLに関してはJOINの条件を付け加えたり適切なWHERE句を付け足しました。  
また、ループ処理中にSQLを発行していた部分はSQLをループの外でまとめて行うようにしました。その結果、SQLの発行を2回に抑え、表示までに30秒程度かかっていたページが5秒程度で表示できるようになりました。

リプレイスの実装にあたってはTDDで開発していくことに挑戦しました。  
テストファーストで実装したことによりテストを書く癖がつきましたし、事前にバグとなりうる場所を察知できてとても開発がしやすかったです。  
何よりテストがしやすい粒度で関数を実装するという意識が持てたのでコードの可読性も上がったと思っています。

### 苦労した点
PHPからのリプレイスだったのでAPIのレスポンスの後、PHP側で正しく処理を繋ぎ込むことも必要でした。  
特に日付のフォーマットやタイムゾーンの違いだったり、truthyとfalsyの判定が違うことで意図しない挙動になることがありました。  
日付のフォーマットやタイムゾーンは重点的にテストを書いたり、適宜Play Groundを使って意図した値になっているかをチェックするようにしました。  
truthyとfalsyの判定の違いなどに気をつけつつ、どういうレスポンスの仕方であるべきかを考慮しながら実装を進めました。

既存のPHPのコードが可読性の低いものであり、そこから内容を読み解くのに非常に苦労しました。  
中には無駄な処理もたくさんあったので、コードから挙動を読み取るだけではなく本来の動きとしてどうあるべきかという観点から「このコードによって本来何が実現したいことなのか」ということを読み解く力がとてもついたと思っています。

また、クリーンアーキテクチャに沿った設計となるようにするため、ファイル構成をどうするかだったりどこのレイヤーに記述を書くべきか、共通化する関数はどこにするべきかを決めるのに非常に苦労しました。  
この辺はクリーンアーキテクチャの本やブログ記事などを読み漁り、どうすればいいかをチームで話し合いながら進めた結果、依存の方向性を一方向にするというクリーンアーキテクチャの原則に沿うようにできました。

</div>
</details>

#### Reactによる検索画面の追加

|key|value|
|---|---|
|プロジェクト規模|2人|
|役割| コーディング / テスト
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Apollo" src="https://img.shields.io/badge/-Apollo%20GraphQL-311C87?style=flat-square&logo=apollo-graphql&logoColor=white" /> <img alt="GraphQL" src="https://img.shields.io/badge/-GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white" /> <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />|

Reactで検索画面の機能追加を行いました。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### 苦労した点
TypeScriptをを使った開発とReduxを使わない開発が初めてだったこと、GraphQLを使っていたのでキャッチアップがとても大変でした。  
これについては本を読んだり公式ドキュメントを何度も読んでキャッチアップしました。

必死にキャッチアップしつつ、保守性や可読性を意識して最終的には以下のようなことを実現できるようになりました。

既存のコードでは何度も同じロジック部分を使用していた部分があり、保守性が低かったので、使いまわせるロジックの部分はcustom hooksを使ってロジック部分を分離するようにしました。  
既存のコードではApollo Clientによるエラーハンドリングが適切に行われていなかったため、ネットワークエラーなどのハンドリングの実装を追加しました。  
TypeScriptの型定義が曖昧になっていた部分があったためきちんと型定義するようにリファクタリングしました。  
tsconfigの設定を見直したり、eslintやCIの設定も見直したことで、チームの開発体験向上に貢献できました。

</div>
</details>

#### マイクロサービスにおける認証機構の構築

|key|value|
|---|---|
|プロジェクト規模|3人|
|役割| 設計 / コーディング / テスト
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Serverless" src="https://img.shields.io/badge/-Serverless Framework-FD5750?style=flat-square&logo=Serverless&logoColor=white" /> <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />|

マイクロサービス化している複数の自社サービスの認証、認可を一元的に管理するための認証アプリを実装しました。  
複数サービス間でログイン状態を共有するためにはどうすればいいかなどを考慮しつつも、セキュアな構成にするため、設計の段階から議論を重ねてアーキテクチャを設計しました。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### 担当した業務
フロントエンドはほぼ1人でReact / TypeScriptを使って実装しました。  
バックエンドの処理もAWS Lambdaを使ってプロトタイプを実装しました。

### 主に実装した機能
- ログイン / ログアウト / パスワード変更 / パスワードリセット / 多要素認証

### 苦労した点
複数のサービス間でログイン状態を共有しつつ、セキュアな構成にするためにはどうすればいいのかという設計が一番難しく、途中で何度も構成が白紙に戻りました。

特に以下の点は現時点でのユースケースだけでなく、将来的にアプリがどうなっていくかを見越してどのアーキテクチャをどういう設定で使うかなどを調査するのに非常に苦労しました。  
- JWTを共有する形にするのか、Cookieを使うのか
- Cookieのセキュリティ設定はどうするべきか
- 複数サービスでログインしている状態でのリフレッシュトークンの扱い方
- 既存のユーザーが今のパスワードでログインできる状態を保ったまま認証機能をリプレイスする

検索してもわからない時は適宜AWSのサポートを利用したり、オンラインで直接アーキテクチャの相談をしたりして決めました。

先に設計をきちんと固めてからプロトタイプを作成するという方針で行い、実際に複数サービス間でログイン情報を共有した状態を作ることができました。

</div>
</details>

### 日本新薬株式会社 (2016/04 ~ 2019/11)
化学者として新規医薬品の研究開発を行なっていました。  

#### 医薬品のサンプル合成、精製
- 新規疾患治療の提案
- サンプルの設計
- サンプルの合成、精製と解析
- 特許出願

### 副業
#### RailsからGoへのリプレイス

|key|value|
|---|---|
|プロジェクト規模|1人|
|役割| 要件定義 / 設計 / コーディング / テスト / 保守・運用
|使用技術| <img alt="Go" src="https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=Go&logoColor=white" /> <img alt="Ruby on Rails" src="https://img.shields.io/badge/-Rails-CC0000?style=flat-square&logo=Ruby on Rails&logoColor=white" /> <img alt="Terraform" src="https://img.shields.io/badge/-Terraform-7B42BC?style=flat-square&logo=Terraform&logoColor=white" /> <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />|

APIモードで動いているRailsアプリケーションの一部をGoにリプレイスするプロジェクトを担当しています。  
Goのコードが何も書かれていない状態から、移行の方針や使用する技術を選定しました。  
副業として業務委託での参画であり、社内にGoに詳しい人がほとんどいなかったため、READMEやNotionに技術の使い方や技術選定の経緯を詳しく書くよう心がけました。

以下に詳細を記述します。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### OpenAPIの運用
RailsからGoにリプレイスするにあたって、まずエンドポイントごとのリクエストとレスポンスの仕様を整理するためにOpenAPIを使用することにしました。  
railsのspecから自動生成するツールなどもありましたが、内容を変更した際に反映されないなど運用面での不安があったので直接定義を書くことにしました。  
ただ、yamlを直接編集するのはあまり効率的な作業ではないため、stoplightというGUI上で編集したものがyamlとして吐き出されるツールを設定して使うようにしました。  

### アーキテクチャとディレクトリ構成
アーキテクチャの設計は概ねクリーンアーキテクチャに沿うような形にしました。  
クリーンアーキテクチャにした理由は、ビジネスロジックをきちんと分離してテストが書けるような状態を作りたかったからです。  
DDDのようなドメインごとにディレクトリ構成を分けるアーキテクチャも考えましたが、移行元のRailsはMVCモデルであり技術的な関心ごとでレイヤーが分かれているアーキテクチャのため、クリーンアーキテクチャの方が移行しやすいというのも理由の1つでした。

クリーンアーキテクチャを踏襲した形にしていますが、実装と運用の都合上改変しているところもあります。  
具体的には、以下のようにしています。  

- presenters層は削除
- controllersからinteractorsを呼び出す際はinterfaceを挟まない

presenters層を削除するとcontrollers層が少しfatになってしまいますが、その代わりに記述がシンプルになるメリットの方が大きいと判断しました。  
全体のテストの方針としてエンドポイント毎のE2Eテストを行う方針にしたので、controllers層の単体テストは不要と判断したため、interactorsはinterfaceを挟まずに呼び出すようにしました。  

#### ファイルの一括生成コマンドの実装
新しいエンドポイントを実装する際に、必要なボイラープレートの記述が多いという課題がありました。  
この課題を解決すべく、text/templateパッケージを使用して、ファイル名を入力すると必要な記述が書かれたファイル群を一括生成できるようなコマンドを作成しました。  

#### DB構造体の自動生成
ORMは人気のあるgormを使用することにしました。  
gormを使用する際にはDBスキーマに相当する構造体をコードベースで定義する必要がありますが、それを自前で定義するのは面倒でもありタイポの危険性もありました。  
調査した結果、gormの開発元にgenというリポジトリがあり、実際のDBスキーマから自動的に構造体を生成するようなバイナリを提供していました。  

DBのマイグレーションはしばらくはRails側で行います。  
実際のDBスキーマから構造体を自動生成できるので実態と乖離することもなく手動で定義する手間も省ける手法を確立できました。

### エラーハンドリングと構造化ログ
エラーハンドリングではログでどこでどのようなエラーが起こったか追えるようにxerrorsを使用して、スタックトレースを出すようにしています。  
呼び出し先でエラーが起こった場合は、呼び出し元でエラー内容をラップした形で返すことでどの関数の呼び出しでエラーが起こったか追えるようにしています。

ログはzapを使用してリクエストの内容を構造化ログとして出力しています。  
エラー時には上述のエラーのスタックトレースも一緒に構造化ログとして組み込むことで、リクエスト内容とエラーの内容を同時に見られるようにしました。

</div>
</details>

#### 名簿アプリの作成


|key|value|
|---|---|
|プロジェクト規模|1人|
|役割| 要件定義 / 設計 / コーディング / テスト / 保守・運用
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Serverless" src="https://img.shields.io/badge/-Serverless Framework-FD5750?style=flat-square&logo=Serverless&logoColor=white" /> <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />|

所属しているオンラインコミュニティのメンバー情報を管理するためのアプリの制作を1人で行いました。  
フロントエンド、バックエンド、インフラの設計から実装、運用まで全てやっており、現在400名以上のユーザーに使用されています。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### アプリの概要
未経験からのエンジニア転職を目指しているコミュニティ生が自分の情報を記載したり、誰かの情報を見たりできる名簿アプリです。

それぞれの契約情報などもマイページから見ることができます。  
欲しい情報を探すために特定のプロフィール情報を持った人を検索できます。  
slackに登録したメールアドレスを入力することでslackのDMで認証コードを送信し、その認証コードによってアプリとslackを連携できます。

### 実装内容
要件定義の段階からインフラやDB設計、フロントエンドとバックエンドの両方を実装しました。  
インフラはできるだけ運用保守のコストを下げることを考え、サーバレスな構成にすることとしました。

- フロントエンド: React / TypeScript
- バックエンド: Serverless Framework / Express / TypeScript
- インフラ: AWS Amplify / API GateWay / Lambda / RDS / DynamoDB

#### フロントエンド
フロントの状態管理はuseState, useReducer + Context APIを使用しました。  
Reduxを使うことも考えましたが、Reduxを使うと非同期処理の実装にthunkやsagaなどのmiddlewareが必要になることや記述量が多くなることを考慮して今回はこのような構成にしました。  
また、React本体が今後Concurrent modeの導入などで非同期処理が扱いやすくなるのではないかとの期待もあり、純正のReact hooksで完結させたかったからです。  
Concurrent modeの導入に先立ち、React Suspenseを使用してみました。

#### バックエンド
slack連携の機能では一時的に認証コードを保持する必要があったのでLambdaとDynamo DBを使用しました。  
認証コードは有効期限があるので、一定の期間で自動的にデータが削除されるようDynamo DBのTTL機能を利用しました。

GitHub Actionsを使用したCI/CDを構築しました。  
CIではTypeScriptのタイプチェック、prettierによるフォーマットチェック、eslintによるlintチェック、ビルドとテスト実行を行なっています。

### 苦労した点
#### フロントエンド
1ページ内で更新すべき値の多いページの読み込みが、遅い状況が起きてしまいました。  
計測した結果、不要な再レンダリングが起こっているためであるとわかったので、React.memoやuseCallback, useMemoを適宜使用し、Contextの粒度を適切に分割することで対応しました。  
実装当初はTypeScriptの理解が浅く、anyを使用した箇所もあったのですが、後々TypeScriptの理解が深まった段階でリファクタリングを行い、anyを一切使用しないコードに修正しました。  
また、tsconfigの見直しも行い、strict: trueにしたりnoImplicitAnyをtrueにしたりできるだけ堅牢な設定になるよう変更しました。

#### バックエンド
今後しばらく使用していくアプリなのでDB設計をきちんと行う必要があると考え、そのために本を4冊ほど読みました。  
データの整合性と検索・更新のパフォーマンスを加味して、レコード数がそれほどまでには多くならないとの推測から、できるだけ整合性を優先させた設計を心がけました。

</div>
</details>

#### Three.jsを用いた3Dアニメーションの描画


|key|value|
|---|---|
|プロジェクト規模|3人|
|役割| コーディング
|使用技術| <img alt="TypeScript" src="https://img.shields.io/badge/-TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white" /> <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Next.js" src="https://img.shields.io/badge/-Next.js-000000?style=flat-square&logo=Next.js&logoColor=white" /> <img alt="Three.js" src="https://img.shields.io/badge/-Three.js-000000?style=flat-square&logo=Three.js&logoColor=white" /> |

物流倉庫の中の荷物の動きを可視化するアプリケーションを実装しました。  
three.jsを使用した3Dアニメーションの描画機能の実装を担当した他、開発環境の整備として各種設定やCIの構築なども行いました。

<details>
<summary style="cursor: pointer">👉  プロジェクト詳細</summary>
<div style="background-color: #f7f7f7; padding: 24px">

### CIの構築
プロジェクトにジョインしてコードを見ていると、TypeScriptの型定義が曖昧なままのコードがあったり、バグの危険性があるコードをいくつか見つけました。  
調べてみるとそれらを未然に防ぐための仕組みが全くなかったので、アサインされたタスクを担当する前にそれらを適切にチェックするための設定やCIの構築をすることを申し出て了承をもらい、これらを構築しました。  
具体的には、prettier, eslint, husky, GitHub ActionsによるCIを構築しました。  
huskyとCIでは型、format、lintのチェックを行い、CIではそれに加えてビルドも行うようにしました。

### 3Dアニメーションの描画
開始時間と終了時間、それぞれの時間での座標データから適切な速度とルートでのアニメーションを描画しました。  
バックエンドで描画に必要なデータを全て計算してレスポンスするとかなり重くなってしまったので、バックエンドではそれらの計算をせず、かつ加工しやすい形でクライアントにレスポンスする必要がありました。そのため、バックエンドの人とどういうレスポンスが必要かを相談し、結果的にデータ加工のしやすさとレスポンス速度を両立させた形になるように設計しました。  
これによりデータを加工する処理は少し複雑になってしまったので、類似の実装で困っていた他のメンバーのためにもコードを共通化できる形で書き共有しました。

</div>
</details>

---

## 業務外活動
### 技術ブログ
日々の業務で詰まったことや、気になったトピックを深掘りしてまとめたりしています。

https://www.sunapro.com/

### 技術ブログの作成
技術ブログを作成しました。  
https://www.sunablog.dev/

使用した技術は以下です。

- React
- Remix
- Mantine (UIライブラリ)
- TailwindCSS
- microCMS

最近ではブログを作成する際はNext.jsを使うのが一般的ですが、Remixを使用して何かを作ってみたかったので試してみました。  
正直ブログが題材ということもあり、あまりRemixの良さを活かせなかったという反省点はありますが、キャッシュについて低レイヤーでコントロールできるため、自分で色々試す中でキャッシュについての理解を深められました。

### OSS貢献
今後積極的にPR作成していこうと思っています。

- issue
  - https://github.com/Hypercontext/linkifyjs/issues/351
- PR
  - https://github.com/faker-js/faker/pull/241

---

## 資格・業績

|取得年|資格・業績名|
|---|---|
|2007/11|実用英語技能検定2級|
|2013/03|薬学部成績優秀賞|
|2017/11|TOEICスコア805点|
|2019/07|G検定(JDLA Deep Learning for GENERAL)|
|2019/11|基本情報技術者|
|2020/02|AWS認定 ソリューションアーキテクトアソシエート|