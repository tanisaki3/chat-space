# README

## users_table
|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|name|string|null: false|
|password|string|null: false|

### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

### Index
- add_index :users, :name

## groups_table
|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|group_name|string|null: false|
|groups_users_id|integer|null: false, foreign_key: true|

### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through: :groups_users

## groups_users_table
|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## messages_table
|Column|Type|Option|
|------|----|------|
|id|integer|null: false|
|body|text|null: false|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


