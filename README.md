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


# テーブル設計

## users テーブル

| Column        | Type    | Options                    |
| ------------- | ------- | -------------------------- |
| nickname      | string  | null: false                |
| email         | string  | null: false, unique: true  |
| password      | string  | null: false                |
| sex_id        | integer | null: false                |
| age_id        | integer | null: false                |


## excuses テーブル

| Column        | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| reason        | string     | null: false                    |
| time          | string     | null: false                    |
| result        | string     | null: false                    |
| category_id   | integer    | null: false                    |
| user          | references | null: false, foreign_key: true |


## tags テーブル

| Column       | Type       | Options                        |
| ------------ | ---------- | ------------------------------ |
| id           | references | null: false, foreign_key: true |
| name         | references | null: false, foreign_key: true |



## excuse_tag_relations テーブル

| Column       | Type       | Options                        |
| ------------ | ---------- | ------------------------------ |
| user         | references | null: false, foreign_key: true |
| item         | references | null: false, foreign_key: true |
