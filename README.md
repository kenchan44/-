# ChatSpace DB設計

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false, index: true,|
|email|string|null: false, unique: true|
|password|integer|null: false|
|group_id|integer|null: false, foreign_key: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

### groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|
### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through: :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

### messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string|null: true,unless: |
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
