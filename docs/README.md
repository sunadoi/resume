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
  <img alt="JavaScript" src="https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=Go&logoColor=white" />

</p>

### フレームワーク・その他
<p>
  <img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" />
  <img alt="Redux" src="https://img.shields.io/badge/-Redux-45b8d8?style=flat-square&logo=redux&logoColor=white" />
  <img alt="Storybook" src="https://img.shields.io/badge/-Storybook-FF4785?style=flat-square&logo=storybook&logoColor=white" />
  <img alt="Vite" src="https://img.shields.io/badge/-Vite-646CFF?style=flat-square&logo=Vite&logoColor=white" />
 <img alt="Apollo" src="https://img.shields.io/badge/-Apollo%20GraphQL-311C87?style=flat-square&logo=apollo-graphql&logoColor=white" />
  <img alt="GraphQL" src="https://img.shields.io/badge/-GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white" />
  <img alt="MySQL" src="https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white" />
  <img alt="Docker" src="https://img.shields.io/badge/-Docker-46a2f1?style=flat-square&logo=docker&logoColor=white" />
  <img alt="AWS" src="https://img.shields.io/badge/-AWS-232F3E?style=flat-square&logo=Amazon AWS&logoColor=white" />
  <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" />
</p>

---

## 職務経歴詳細

### 株式会社TERASS (2021/05 ~ 現在)
#### 開発環境の整備

|key|value|
|---|---|
|プロジェクト規模|1人|
|役割|設計 / コーディング / 運用・保守|
|使用技術|<img alt="React" src="https://img.shields.io/badge/-React-45b8d8?style=flat-square&logo=react&logoColor=white" /> <img alt="Vite" src="https://img.shields.io/badge/-Vite-646CFF?style=flat-square&logo=Vite&logoColor=white" /> <img alt="Storybook" src="https://img.shields.io/badge/-Storybook-FF4785?style=flat-square&logo=storybook&logoColor=white" /> <img alt="Firebase" src="https://img.shields.io/badge/-Firebase-FFCA28?style=flat-square&logo=Firebase&logoColor=white" /> <img alt="Renovate" src="https://img.shields.io/badge/-Renvate-1A1F6C?style=flat-square&logo=Renovatebot&logoColor=white" />|


担当タスク以外にもやりたいことがあって認められればできるという環境だったので、いくつかの提案をして実行しました。具体的には次のことをやりました。

- Firebase preview channelの設定
- storybookのデプロイ環境の構築
- webpackからviteへのリプレイス
- Renovateの導入
- Vitestの導入

<details>
<summary>プロジェクト詳細</summary>
<div>

## Firebase preview channelの設定
storybookのデプロイ環境の構築とビジュアルリグレッションテスト
webpackからviteへのリプレイス
Renovateの導入
Firebase preview channelの設定
機能を実装したときにGit操作ができないPdMに仕様を画面上で確認してもらいたい、細かいUI上の修正を簡単に画面上で確認したいということが度々ありました。
これを解決するためにPR作成時にそのPR内容を反映したものを一時的にデプロイしてくれるようなサービスがないかと考えました。AWS Amplifyではそういう機能があったのでFirebaseにも似たような機能がないか探したところ、Firebase preview channelというものがありました。
GitHub ActionsでPRにpushした際に最新のPRの内容を反映したものをデプロイするように設定をし、PRを閉じたときに削除するよう設定しました。
これによってPRで発行されたURLをクリックするだけでPR内容を確認できる環境ができ、開発体験が向上したと思っています。
こちらの内容はブログにまとめました
https://www.sunapro.com/github-actions-firebase-preview/

## storybookのデプロイ環境の構築
storybookを使用しているものの、localにしか環境が存在しなかったためlocalでわざわざ立ち上げなくても最新の内容を確認できる環境が欲しかったので用意することにしました。
FIrebaseのHostingを使ってstorybook用のホスティングを用意することを最初考えたのですが、チーム内でしか見れないprivateのものにしたいという要件があったため、認証周りの設定が複雑になりそうでした。
調査した結果、chromaticというサービスを見つけこれであればGitHub Actionsを使ってマージ時に自動でデプロイできるようになるだけでなく、スナップショットを用いたビジュアルリグレッションテストによって意図しないスタイリングの崩れも検知できる仕組みを整えることができました。
実際その後のQA作業でリリース前に意図しないスタイリングの崩れを検知できました。

## webpackからviteへのリプレイス
localでのサーバーの立ち上げがとても遅く毎回1分近くかかるという課題がありました。調べてみるとViteというビルドツールがあることを知り、これは外部ライブラリはesbuildを使った高速なバンドル、ソースコードはバンドルをしないでES Modulesをそのまま読み込むのでとても速いというものだったので、ちょうど要件にあっていると思いこちらへのリプレイスを行いました。
結果的に1分近くかかっていたサーバーの立ち上げが3秒程度になったので非常に快適な開発環境が整ったと思っています。
こちらの内容はブログにまとめました。
https://www.sunapro.com/webpack-to-vite/

## Renovateの導入
プロジェクトのライブラリのバージョンが古いものがいくつかあり、機能開発する上でそれが原因でバグが生じることが何度かありました。こういった背景からライブラリの定期的なアップデートをしたいということになり、どういった技術があるのか調査しました。
DependabotやRenovateなどが代表的なツールであり、これらは定期的にライブラリのアップデートを監視してくれてPRを作成してくれますが、設定の細かさやPRの情報のリッチさなどからRenovateを採用することにしました。
これによりライブラリが新しい状態を保つことができるようになっただけでなく、ライブラリの変更をきちんと追いかけるようになったのは良い副産物でした。
また、ライブラリのアップデートによってテストが落ちたことがあり、ライブラリ側のデグレーションらしき挙動だったのでissueを立てて修正してもらいました。
ref: https://github.com/Hypercontext/linkifyjs/issues/351

## Vitestの導入
firestoreのrulesをテストする際にjestを使用していたのですが、watchモードでの変更の反映に20秒程度かかるという課題がありました。非常に開発効率が悪かったためちょうど開発され始めたvitestという非常に高速で動作するテスティングライブラリを使用することにしました。結果、watchモードでの変更の反映が1秒程度となり開発効率が非常に向上しました。
まだproduction readyではないものの、問題が起きたらjestに戻すという合意形成のもと、全てのテストをvitestで動作するようにリプレイスしました。結果的にテストを書くモチベーションも上がり、非常に良い開発体験を得られたと思っています。
</div>
</details>