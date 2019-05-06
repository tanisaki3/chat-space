# README

## users_table
|Column|Type|Option|
|------|----|------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: :groups_users

### Index
- add_index :users, :name

## groups_table
|Column|Type|Option|
|------|----|------|
|name|string|null: false|
|message_id|references|foreign_key: true|

### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through: :groups_users

## groups_users_table
|Column|Type|Option|
|------|----|------|
|group_id|references|foreign_key: true|
|user_id|references|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## messages_table
|Column|Type|Option|
|------|----|------|
|body|text|
|image|string|
|user_id|references|foreign_key: true|
|group_id|references|foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


