# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

 ### Association
 - has_many : prototypes
 - has_many : comments


## prototypes テーブル

| Column     | Type         | Options                         |
| ---------- | ------------ | ------------------------------- |
| title      | string       | null: false                     |
| catch_copy | string       | null: false                     |
| concept    | string       | null: false                     |
| user       | references   | null: false, foreign_key: true  |

 ## Association
- has_many   :comments
- belongs to :user


## comments テーブル

| Column     | Type         | Options                        |
| ---------- | ------------ | ------------------------------ |
| text       | text         | null: false                    |
| user       | reference    | null: false, foreign_key: true |
| prototype  | reference    | null: false, foreign_key: true |

 ## Association

- belongs to :user
- belongs to :prototype