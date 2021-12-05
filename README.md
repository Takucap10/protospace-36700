# README

# プロトスペースのテーブル設計

## Userテーブル

| Column              | Type   | Options                    |
| ------------------- | ------ | -------------------------- |
| email               | string | null: false , unique: true |
| encrypted_ password | string | null: false                |
| name                | string | null: false                |
| profile             | text   | null: false                |
| occupation          | text   | null: false                |
| position            | text   | null: false                |

### Association

- has_many : prototypes
- has_many : comments

## prototypesテーブル

| Column              | Type      | Options           |
| ------------------- | --------- | ----------------- |
| title               | text      | null: false       |
| catch_copy          | text      | null: false       |
| concept             | text      | null: false       |
| user                | reference | foreign_key: true |

### Association

- has_many : comments
- belongs_to : user

## commentsテーブル

| Column              | Type      | Options           |
| ------------------- | --------- | ----------------- |
| content             | text      | null: false       |
| prototype           | reference | foreign_key: true |
| user                | reference | foreign_key: true |

### Association

- belongs_to : user
- belongs_to : prototypes