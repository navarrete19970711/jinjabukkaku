# テーブル設計


## usersテーブル
| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| name               | string | null: false               |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |


### Association
- has_many :post



## placesテーブル
| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| name               | string | null: false               |
| deity              | string | null: false               |
| station            | string | null: false               |
| address            | string | null: false               |
| latitude           | float  | null: false               |
| longitude          | float  | null: false               |


### Association
- has_many :post



## postsテーブル
| Column             | Type       | Options                        |
| ------------------ | ---------- | ------------------------------ |
| text               | text       | null:false                     |
| user               | references | null: false, foreign_key: true |
| place              | references | null: false, foreign_key: true |


### Association
- belongs_to :user
- belongs_to :place