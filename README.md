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
|group_id|integer|foreign_key: true|

### Association

- belongs_to :user
- belongs_to :group

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|integer|null:false|

### Association

- has_many :users,through:groups_users
- has_many :post
- has_many :groups_users

## users_groupsテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false,foreign_key:true|
|groups_id|integer|null:false,foreign_key:true|
### Association

- belongs_to :group 
- belongs_to :user


