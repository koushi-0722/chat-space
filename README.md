# README

usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|name|string|null: false|
Association
has_many :groups
belongs_to :message
has_many :users_groups
has_many :groups through: :users_groups

messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|string||
|image|string||
|user_id|integer|null: false, foreign_key: true|
Association
belongs_to :user
has_many :groups

groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|null: false|
Association
has_many :users through: :users_groups
has_many :meassages
has_many :users_groups

users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|foreign_key: true|
|group_id|integer|foreign_key: true|
Association
belongs_to :group
belongs_to :user