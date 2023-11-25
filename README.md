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

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| nickname           | string | null: false |
| email              | string | null: false |
| password           | string | null: false |
| user_namekanji     | string | null: false |
| user_namekana      | string | null: false |
| birthday           | string | null: false |
| id                 | string | null: false |




## products　テーブル

| Column             | Type       | Options                        |
| ------------------ | ------     | -----------                    |
| product_name       | string     | null: false                    |
| price              | string     | null: false                    |
| user               | references | null: false, foreign_key: true |
| category           | string     | null: false                    |
| condition          | string     | null: false                    |
| shipping_charges   | string     | null: false                    |
| address            | string     | null: false                    |
| deliverytime       | string     | null: false                    |
| image              | string     | null: false                    |
| explanation        | string     | null: false                    |

### Association
- belongs_to :user



## shipping_address テーブル

| Column             | Type       | Options                        |
| ------------------ | ------     | -----------                    |
| post_code          | string     | null: false                    |
| prefecture         | string     | null: false                    |
| municipality       | string     | null: false                    |
| street_address     | string     | null: false                    |
| building_name      | string     | null: false                    |
| phone_number       | string     | null: false                    |
| user               | references | null: false, foreign_key: true |

### Association
- belongs_to :user




### purchase_record　テーブル

| Column             | Type   | Options                            |
| ------------------ | ------ | -----------                        |
| user               | references | null: false, foreign_key: true |

### Association
- belongs_to :user