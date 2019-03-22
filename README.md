# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

## usersテーブル

|Column|Type|Options|
|------|----|-------|
|id|integer||
|name|string|unique: true, null: false|
|email|string|unique: true, null: false|
|password|string|unique: true, null: false|

### Association
- has_many :groups, through: :members

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer||
|name|string|unique: true, null: false|

### Association
- has_many :users, through: :members

## membersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group
- has_many :messages

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer||
|body|text|null: false|
|image|text||
|timestamps|datetime|null: false|
|member_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :member


* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
