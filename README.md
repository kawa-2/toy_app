# README

## 第2章

#### 概要

toyアプリケーションを新規作成し、scaffold機能を使用しユーザーとマイクロポストのデータを作成。<br>
作成したwebアプリケーションでユーザー登録、マイクロポストが新規作成できる仕組みを学習。<br>
コードに、文字数制限・空でcreateできないようバリデーションを追加。

#### 学習事項

* 生成したファイルをリモートリポジトリへプッシュする方法
```
$ git remote add origin git@〜〜:<username>/<ディレクトリ名>.git
$ git push -u origin --all
```
* Railsはアプリケーションの構成にMVC (Model-View-Controller) を採用している
* scaffoldはアプリケーションの雛形を生成してくれるジェネレーター<br>
以下コマンドでUserのデータモデルが生成される（以下はnameとemailをパラメータに追加している）
```
$ rails generate scaffold User name:string email:string
```
* REST(REpresentational State Transfer)アーキテクチャ<br>
└ RESTは、インターネットそのものやWebアプリケーションなどを構築するためのアーキテクチャのスタイルの1つ<br>
RailsにおけるRESTとは、アプリケーションを構成するコンポーネント (ユーザーやマイクロポストなど) を「リソース」としてモデル化することを指す。<br>
CRUD（クラッド）、HTTP requestメソッドに対応<br>
→　このスタイルを採用することで設計が楽になる。


#### つまづき箇所

* rails consoleの使い方<br>
rails consoleはRailsアプリケーションを対話的に操作することができる。
ただ、CREAT、INSERTなどができてしまうので、確認したいだけであればirbを使った方が良い。

* Herokuへのpushが　$ git push heroku だと下記メッセージが出てpushできず。<br>
$ git push heroku master と書けばpushできた。<br>
```
fatal: You are pushing to remote 'heroku', which is not the upstream of
your current branch 'master', without telling me what to push
to update which remote branch.
```



#### メモ

* マイグレーション
Rails4以前のバージョンではrailsコマンドではなくrakeコマンドを使う必要がある。
```
Rails5
 $ rails db:migrate

Rails4以前
 $ bundle exec rake db:migrate
```

* このリポジトリのHeroku 
https://enigmatic-citadel-01574.herokuapp.com/
