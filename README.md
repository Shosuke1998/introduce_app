# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |

### Association

- has_many :posts
- has_many :comments


## posts テーブル

| Column          | Type         | Options                        |
| ----------------| ------------ | ------------------------------ |
| text            | text         | null: false                    |
| title           | string       | null: false                    |
| user            | references   | null: false, foreign_key: true |
| department_id   | integer      | null: false                    |

### Association

- belongs_to :users
- has_many :comments


## comments テーブル

| Column | Type       | Options                        |
| ------ | ---------- | ------------------------------ |
| text   | text       | null: false                    |
| user   | references | null: false, foreign_key: true |
| post   | references | null: false, foreign_key: true |


### Association

- belongs_to :post
- belongs_to :user

