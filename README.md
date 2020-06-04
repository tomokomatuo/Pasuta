# README

自分に似合う洋服のスタイリングがわからない人、自分の服のセンスに自信がない人のためにパーソナルスタイリスト（服アドバイザー）を派遣するマッチングアプリ。
* 就業タームのスキル　1.AWS 2.フォローフォロワー機能
* カリキュラム外の技術　Gemのratyrate

以上を実装予定です。

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

|      | 　　　　　　　　　　　　機能説明　                |  優先度  |          　　目的
| ---- | --------------------------------------------| ------- | ---------------------------------------------- |
|  1   | 　アドバイザー・ユーザーの詳細画面を閲覧できる　　　 |    高   |  詳細画面を見ることで、自分の好みにマッチする人を選べる |
|  2   |  アドバイザー・ユーザーの一覧表示ができる　　　　　　|    高   | 　一覧を作ることで、多くの選択肢を選ぶことができる      |
|  3   |  アドバイザー・ユーザー共に星５つによる評価ができる  |    高   |  星評価で見た目も可愛く、評価の高い人を選べる         |
|  4   |  アドバイザー・ユーザーのレビューが書ける          |    高   |  自分にマッチする人を選ぶために重要                  |
|  5   |  アドバイザー・ユーザーが各自の詳細画面を編集できる  |    高   |  相手に自分のスタイルをアピールするため              |
|  6   |  ユーザー・アドバイザーのフォローフォロワー機能     |    高   | 　フォローすることによって、アプローチや宣伝になる      |
|  7   |  退会できる                                   |    高   | 　気に入らなければ退会できる                        |
|  8   |  メッセージのやりとりができる                    |    高   | 　詳細画面でわからないことが直接聞ける                |
|  9   |  ログイン機能がある                            |    高　　| 　プライバシーを守れる                             |
|  10  |  アドバイザー・ユーザーのソート機能               |    高   |  ユーザー・アドバイザー共に自分の条件を絞れる          |
|  11  |  OAuthを利用したログイン機能                    |    中   |  手軽にログインできるようになる                      |
|  12  |  アドバイザーランキング（指名数によりカウント）     |    低   |  ユーザーがアドバイザーを選びやすくなる               |
|  13  |  アドバイザーのスケジュール機能（時間があれば)      |    低   |  ユーザーはアドバイザーの空いてる時間を知ることができる  |


## テーブル定義書

* テーブル

<<<<<<< HEAD
|      |   テーブル理論名    |    物理名     |                     備考                                           　　　 |
=======
|      |   テーブル理論名    |    物理名      |                     備考                                           　　　|
>>>>>>> e0f9fddaedbe8c7d4c8c0f8ed77694147fcbaf78
| ---- | ---------------- | ------------- | ----------------------------------------------------------------------- |
|  1   |  User情報         | User          |  ユーザーさんの基本ステータスを管理する。アドバイザーは（adviserカラムをtrueにする）       |
|  2   |  relationship情報 | relationship  |  フォローフォロワー機能を作るためのテーブル                                       |
|  3   | converstaion情報  | Conversation  |  誰と誰の会話かを区別するためのテーブル　　　                                   |
|  ４   |  message情報      |  Message      |   複数の文章を管理するテーブル                                               |  
|  5   |  review情報       |  Review       |  レビューを管理するテーブル                                                   |   


* Userカラム

<<<<<<< HEAD
|      |   カラム理論名 |  カラム物理名      |    型    |  桁  | NOTNULL  | 主キー | index | コメント                       |
| ---- | -------------| ---------------- | -------- |-----| -------- |------ |-------|------------------------------ |
|  1   |  ユーザーid   |     id           |  integer |      |   true   | true  |       |  ユーザー id                   | 
|  2   |  名前　　     |    name          |  string  |      |  true    |       |       |   ユーザー名       　　　       |
|  3   |  email       |   email          |  string　|　    |   true   |       |       |    ユーザーアドレス              |
|  ４  |  年齢         |    age           |  string  |      |   true  |        | true  |   セレクトボックスで選ぶ         |      
|  5   |  住所        |   address         |  string  |     |   true   |       |        |  ユーザーの居住地               |
|  6   |  ユーザーicon |       icon        |  image   |     |          |      |         |  ユーザーの画像                |
|  7   |  服の写真     | clothes_image     |  image　 |     |          |       | true   |  アドバイザースタイリング写真     |
|  9   |  アドバイザー |    adviser         | boolean  |     |  true   |       |        | 　ユーザーを区別する             |
|  6   |  自己紹介　　 |  content           | text     |     |         |       |        |  お悩みなどを記載               |
|  7   |  電話番号    | phone_number       |  string　 |     |   true  |       |        |　ユーザーのコンタクト情報         |
|  8   |  OAuth      |  provider          |  string  |     |         |       |         |                              |
|  9   |  OAuth      |    uid             | string   |     |         |       |         |                              |
|  10  |  OAuth　　   | sign_in_count      | text     |     |         |       |         |                             |
|  11  |  OAuth      | current_sign_in_at  | datetime |    |          |      |         |                              |
|  12  |  OAth       | last_sign_in_at     | datetime |    |          |       |        |                              |       
|  13  |  OAuth      | current_sign_in_ip  |  inet    |    |          |       |        |                              |
|  14  |  OAth       | last_sign_in_ip     |  inet    |    |          |       |        |                              |  
|  15  |  パスワード   | password_digit      |  integer |    |   true   |       |        | パスワード認証                 |
|  16  |  性別   　　　| gender              |  integer |    |   true   |       |        |  セレクトボックスで選ぶ         |  
=======
|      |   カラム理論名 |  カラム物理名        |    型    |  桁  | NOTNULL  | 主キー | index | コメント                       |
| ---- | ------------| ------------------ | --------|------| -------- |------ |-------|---------------------------- |
|  1   |  ユーザーid   |     id            |  integer |      |   true   | true  |       |  ユーザー id                 | 
|  2   |  名前　　     |    name           |  string  |      |  true    |       |       |   ユーザー名       　　　     |
|  3   |  email      |   email            |  string　|　    |   true   |       |       |    ユーザーアドレス             |
|  ４   |  年齢        |    age             |  string  |     |   true   |       | true  |   セレクトボックスで選ぶ          |      
|  5   |  住所        |   address          |  string  |     |   true   |       |       |  ユーザーの居住地              |
|  6   |  ユーザーicon |       icon         |  image   |     |          |       |       |  ユーザーの画像                |
|  7   |  服の写真     | clothes_image      |  image　 |     |          |       | true  |  アドバイザースタイリング写真       |
|  9   |  アドバイザー   |    adviser         | boolean  |     |  true    |       |       | 　ユーザーを区別する             |
|  6   |  自己紹介　　  |  content           | text     |     |          |       |       |  お悩みなどを記載               |
|  7   |  電話番号     | phone_number       |  string　 |     |   true   |       |       |　ユーザーのコンタクト情報          |
|  8   |  OAuth       |  provider          |  string  |     |          |       |        |                             |
|  9   |  OAuth       |    uid             | string   |     |          |       |        |                             |
|  10  |  OAuth　　    | sign_in_count      | text     |     |          |       |        |                             |
|  11  |  OAuth       | current_sign_in_at | datetime |     |          |       |        |                             |
|  12  |  OAth        | last_sign_in_at    | datetime |     |          |       |        |                             |       
|  13  |  OAuth       | current_sign_in_ip |  inet    |     |          |       |        |                             |
|  14  |  OAth        | last_sign_in_ip    |  inet    |     |          |       |        |                             |  
|  15  |  パスワード     | password_digit     |  integer |     |   true   |       |        | パスワード認証                 |
|  16  |  性別   　　　 | gender             |  integer |     |   true   |       |        |  セレクトボックスで選ぶ           |  
>>>>>>> e0f9fddaedbe8c7d4c8c0f8ed77694147fcbaf78

* Relationshipカラム

|      |   カラム理論名 |  カラム物理名      |    型    |  桁  | NOTNULL  | 主キー | index | コメント                       |
| ---- | -------------| ---------------- | -------- |-----| -------- |------ |-------|------------------------------ |
|  1   |  フォロワーid  |   follower_id    |  integer |     |          |       |       |  フォローする側                 | 
|  2   |  フォロー id   |    followed_id   |  integer |     |          |       |       |  フォローされる側       　　　   |

* Messageカラム

|      |   カラム理論名 |  カラム物理名      |    型    |  桁  | NOTNULL  | 主キー | index | コメント              |
| ---- | -------------| ---------------- | -------- |-----| -------- |------ |-------|--------------------- |
|  1   |  会話id   　　|  conversation_id |  integer |      |   true   | true  |       |  会話の id            | 
|  2   |  ユーザーid　　|   user_id        |  integer |      |  true    |       |       |   ユーザーid       　 |
|  3   |    内容    　　|   body           |  text　  |　    |   true   |       |       |   会話の本体           |
|  4   |    既読    　　|   read           |  boolean |　    |   true   |       |       |  受け手が読んだかどうか  |

* Conversationカラム

|      |   カラム理論名 |  カラム物理名      |    型    |  桁  | NOTNULL  | 主キー | index | コメント              |
| ---- | -------------| ---------------- | -------- |-----| -------- |------ |-------|--------------------- |
|  1   |  センダーid    |  sender_id       | integer |     |   true   | true  | true  |  送り手 id            | 
|  2   |  受け手id　　  |   recipient_id   |  integer |     |  true    | true  |  true |   受け手　id      　   |

* Reviewカラム

|      |   カラム理論名 |  カラム物理名      |    型    |  桁  | NOTNULL  | 主キー | index | コメント              |
| ---- | -------------| ---------------- | -------- |-----| -------- |------ |-------|--------------------- |
|  1   |  ユーザーid   |  user_id         |  integer |      |  true    | true  |       | 1対多アソシエーション　 |
|  2   |  レビュー情報　|   comment        |  text    |      |  true    |       |       |   レビューの内容     　|




## ER図

<img width="1440" alt="スクリーンショット 2020-06-04 11 50 35" src="https://user-images.githubusercontent.com/61731127/83709508-ae9c4b00-a659-11ea-9415-aa01b3f3ab44.png">

## 画面遷移図

<img width="1440" alt="スクリーンショット 2020-06-04 11 34 11" src="https://user-images.githubusercontent.com/61731127/83708609-9c211200-a657-11ea-864c-17fd511e9ae3.png">

## ワイヤーフレーム

<img width="1440" alt="スクリーンショット 2020-06-01 19 16 46" src="https://user-images.githubusercontent.com/61731127/83399638-7ff55900-a43c-11ea-8544-d085477475b3.png">
<img width="1440" alt="スクリーンショット 2020-06-04 12 09 21" src="https://user-images.githubusercontent.com/61731127/83710716-50bd3280-a65c-11ea-8a6c-78ab56487f51.png">
<img width="1440" alt="スクリーンショット 2020-06-01 19 47 52" src="https://user-images.githubusercontent.com/61731127/83401906-cb116b00-a440-11ea-8e38-6d47f04c897d.png">


## 使用予定Gem

デフォルトで導入されているgemに加え、以下の物を使用する。

* impressionist アドバイザーのランキング（使用未定）
* ratyrate 星５つの評価をつける
* gem 'devise'
* gem 'omniauth'
* gem 'omniauth-google-oauth2'
