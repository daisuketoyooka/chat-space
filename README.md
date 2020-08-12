# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false,unique:true|
|password|integer|null: false|
|email|string|null:false|

### Association
- has_many groups,through:members
- has_many :posts
- has_many :groups_users

## postsテーブル

|Column|Type|Options|
|------|----|-------|
|text|text||
|image|text||
|user_id|integer|foreign_key: true|

### Association

- belongs_to: user
- has_many: groups

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|text|text|null:false|
|member|string|null:false,unique:true|
|user_id|integer|null:false,foreign_key: true|

### Association

- has_many:users
- belongs_to: post
- has_many:groups_users 

## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false,foreign_key:true|
|groups_id|integer|null:false,foreign_key:true|
### Association

- belongs_to:group 
- belongs_to:user


