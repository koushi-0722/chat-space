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

usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|username|string|null: false|
Association
has_many :group
belongs_to :message

messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|text|null: false|
|iamge|text||
|user_id|integer|null: false, foreign_key: true|
Association
belongs_to :users
has_many :group

groupテーブル
|Column|Type|Options|
|------|----|-------|
|groupname|null: false|
Association
has_many :users
has_many :meassage

users_groupテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|text|text|null: false|
Association
has_many :group
has_many :user