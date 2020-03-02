# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...


#chat-space DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
- has_many :tweets
- has_many :groups
- has_many :groups_tweets

## tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- has_many :groups_tweets

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|groups_name|string|null: false|
|user_id|string|null: false|
### Association
- has_many :groups_tweets
- belongs_to :user

## groups_tweetsテーブル
|Column|Type|Options|
|------|----|-------|
|text_id|integer|null: false, foreign_key: true|
|image_id|integer|null: false, foreign_key: true|
|groups_name_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :tweet
- belongs_to :group
- belongs_to :user

