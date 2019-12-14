# ChatSpace DB設計

### usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|integer|null: false, foreign_key: true|
|email|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- has_many :messages
- has_many :groups, through: :groups_users

### groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many :messages
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
|image|string||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user
