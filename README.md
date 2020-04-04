## usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_name|string|null:false,unique:true|
|mail_adress|string|null:false,unique:true|
|password|string|null:false|

### Association
- has_many:groups,throgh:users_groups
- has_many:messages
- has_many:users_groups

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|user_id|references|null:false,foreign_key:true|
|group_id|references|null:false,foreign_key:true|

### Association
- belongs_to:user
- belongs_to:group

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null:false|

### Association
- has_many:messages
- has_many:users_groups
- has_many:users,through:users_groups

## users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false,foreign_key:true|
|group_id|integer|null:false,foreign_key:true|

### Association
- belongs_to:group
- belongs_to:user
