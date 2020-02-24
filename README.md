## messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|text|null: false, |
|image|sting|null: false, |
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
  belongs_to :group

## usersテーブル

|name|string|null: false, unique:true|
|email|string|null: false, unique:true|

### Association
has_many :messages
has_many :groups_users
has_many :groups, through: :groups_users

## groupsテーブル

|name|string|null: false, |

### Association
has_many :messages
has_many :groups_users
has_many :users, through: :groups_users

## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user