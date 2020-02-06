# データベース設計

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|pw|string|null: false|

### Association
- has_many :messages
- has_many :user_chat_group
- has_many :chat_group

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|integer|null: false, foreign_key: true|
|chat_group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :chat_group

## chat_groupテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :messages
- has_many :user_chat_group
- belongs_to :user

## user_chat-groupテーブル

|Column|Type|Options|
|------|----|-------|
|chat_group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :chat_group
- belongs_to :user