# データベース設計

## userテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|pw|string|null: false|

### Association
- has_many :messages
- has_many :user_chat-group

## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false|
|image|string||
|user_id|integer|null: false, foreign_key: true|
|chat-group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :chat-group

## chat-groupテーブル

|Column|Type|Options|
|------|----|-------|
|group-name|string|null: false|

### Association
- has_many :messages
- has_many :user_chat-group

## user_chat-groupテーブル

|Column|Type|Options|
|------|----|-------|
|chat-group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :chat-group
- belongs_to :user