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


# Database Design

## users table

|Column|Type|Options|
|------|----|-------|
|name|string|unique: true, null: false, add_index :users, :name|
|email|string|unique: true, null: false|
|password|string|unique: true, null: false|

### Association
- has_many :groups, through: :members
- has_many :members
- has_many :messages

## groups table
|Column|Type|Options|
|------|----|-------|
|name|string|unique: true, null: false|

### Association
- has_many :users, through: :members
- has_many :members
- has_many :messages

## members table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## messages table
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|text||
|timestamps|datetime|null: false|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null:false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


