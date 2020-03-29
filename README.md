## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|index: true, foreign_key: true, null: false|
|group_id|integer|index: true, foreign_key: true, null: false|

### Association
- belongs_to :group
- belongs_to :user
- belongs_to :user

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false,unique: true|
|mail|string|null:false,unique: true|
|passward|string|null: false|

### Association
- has_many :groups,through:groups_users
- has_many :messages
- has_many :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|strings|null: false|

### Association
- has_many :users, through: :uesrs_groups
- has_many :messages
- has_many :users_groups 

### messageテーブル
|Column|Type|Options|
|------|----|-------|
|boby|text||
|image|string||
|group_id|references|null: false, foreign_key: true|
|user_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
