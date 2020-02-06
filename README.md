# データベース設計

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|pw|string|null: false|

### Association
- has_many :messages
- has_many :user_groups

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|groups_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :user_groups

## user_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|groups_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :chat_group
- belongs_to :user