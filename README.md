# ChatSpace DB設計

### userテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|email|integer|null: false, foreign_key: true|
|password|integer|null: false, foreign_key: true|
### Association
- has_many :body
- has_many :image
- has_many :group

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user

### groupテーブル
|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- has_many :user, through: :groups_users

### create-groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false|

### Association
- has_many :user_id

### edit-groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false|
|user_id|integer|null: false|
### Association
- has_many :user_id

### edit-accountテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer||
|email|integer|null: false|





