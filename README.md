## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false, |
|image|sting|null: false, |

### Association
- belongs_to :users

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, |
|user_name|string|null: false, unique:true|
|user_email|string|null: false, unique:true|

### Association
has_many :messages
has_many : groups, through: :groups_users

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_id|integer|null: false, |
|group_name|string|null: false, |

### Association
- has_many :users, through: :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user