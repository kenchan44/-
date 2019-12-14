# ChatSpace DB設計

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false, foreign_key: true|
|email|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- has_many :groups, through: :groups_users

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

### groupsテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
### Association
- belongs_to :group
- has_many :users, through: :groups_users

### create-groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false|
### Association
- has_many :users

### edit-groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false|
|name|integer|null: false|
### Association
- has_many :users

### edit-usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer||
|email|integer|null: false|
### Association
- has_many :users
