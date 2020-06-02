# README

自分に似合う洋服のスタイリングがわからない人、自分の服のセンスに自信がない人のためにパーソナルスタイリスト（服アドバイザー）を派遣するマッチングアプリ。
* 就業タームのスキル　1.AWS 2.フォローフォロワー機能
* カリキュラム外の技術　Gemのratyrate

以上を実装予定です。

## バージョン情報
* Ruby 2.6.5
* Ruby on Rails 5.2.4
* psql (PostgreSQL) 12.2

## カタログ設計
* アプリ名　「 Pasuta（パスタ）」
* フロントはReactサーバーはAWSを使用(予定)
* コンセプトは洋服を着こなしたいが着方がわからない一般ユーザーのために、スタイリングに自信のある個人（プロ・アマ不問）が自分のセンスを生かして一般ユーザーにアドバイスすることである。実際に店に行って洋服を見て回るので、友達が自分のために服を選んでくれているような感覚になれる。

## 機能一覧
|      | 　　　　　　　　　　　　機能説明　                               |  優先度  | 
| ---- | ---------------------------------------------------------- | ------- | 
|  1   |  アドバイザーは自己紹介、得意なスタイリング等をユーザー側に紹介できる。     |    高   |  
|  2   |  ユーザーは自分のお悩みを表示して、アドバイザーを募ることができる。         |    高   | 
|  3   |  アドバイザー・ユーザー共に星５つによる評価とレビューを書く欄がある。         |    高   |  
|  4   |  料金はアドバイザー側が提示する。電車代込等                          |    高   |  
|  5   |  退会できる。                                                  |    高   |  
|  6   |  ユーザー・アドバイザーのフォローフォロワー機能                         |    高   | 
|  7   |  アドバイザーによるイメージ画像アップロード                            |    中   |  
|  8   |  メッセージのやりとりができる。                                     |    中   |  
|  9   |  OAuthを利用したログイン機能                        　　　　　    |    中   |  
|  10  |  アドバイザーランキング（指名数によりカウント）                          |    低   |  
|  11  |  アドバイザーのスケジュール機能（時間があれば)                        |    低   |  




## テーブル定義書
|      |   テーブル理論名    |    物理名     |                     備考                                           　　　|
| ---- | ---------------- | ------------- | ---------------------------------------------------------------------- |
|  1   |  User情報         | User         |  ユーザーさんの基本ステータスを管理する。アドバイザーは（adviserカラムをtrueにする）|
|  2   |  relationship情報 | relationship |  フォローフォロワー機能を作るためのテーブル                                    |
|  3   | converstaion情報  | Conversation |  誰と誰の会話かを区別するためのテーブル　　　                                  |
|  ４  |  message情報      |  Message     |   複数の文章を管理するテーブル                                               |  
## ER図

<img width="1440" alt="スクリーンショット 2020-06-01 19 00 32" src="https://user-images.githubusercontent.com/61731127/83398404-41f73580-a43a-11ea-9606-381b53de1d71.png">

## 画面遷移図

<img width="1440" alt="スクリーンショット 2020-06-01 17 03 51" src="https://user-images.githubusercontent.com/61731127/83388983-61866200-a42a-11ea-9982-55c41e98de8d.png">

## ワイヤーフレーム

<img width="1440" alt="スクリーンショット 2020-06-01 19 16 46" src="https://user-images.githubusercontent.com/61731127/83399638-7ff55900-a43c-11ea-8544-d085477475b3.png">
<img width="1440" alt="スクリーンショット 2020-06-01 19 31 16" src="https://user-images.githubusercontent.com/61731127/83400818-7d93fe80-a43e-11ea-8690-4469f161ce4a.png">
<img width="1440" alt="スクリーンショット 2020-06-01 19 47 52" src="https://user-images.githubusercontent.com/61731127/83401906-cb116b00-a440-11ea-8e38-6d47f04c897d.png">


## 使用予定Gem

デフォルトで導入されているgemに加え、以下の物を使用する。

* impressionist アドバイザーのランキング（使用未定）
* ratyrate 星５つの評価をつける
* gem 'devise'
* gem 'omniauth'
* gem 'omniauth-google-oauth2'
