# テーブル設計
## usersテーブル

| Column     | Type   | Option   | 
| ---------- | ------ | -------- | 
| email      | string | Not Null | 
| password   | string | Not Null | 
| name       | string | Not Null | 
| profile    | text   | Not Null | 
| occupation | text   | Not Null | 
| position   | text   | Not Null | 

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column     | Type      | Option                         | 
| ---------- | --------- | ------------------------------ | 
| title      | string    | Not Null                       | 
| catch_copy | text      | Not Null                       | 
| concept    | text      | Not Null                       | 
| user       | reference | null: false, foreign_key: true | 

### Association
- belongs_to  :users
- has_many    :comments

## commentsテーブル

| Column    | Type      | Option                         | 
| --------- | --------- | ------------------------------ | 
| text      | text      | Not Null                       | 
| user      | reference | null: false, foreign_key: true | 
| prototype | reference | null: false, foreign_key: true | 

### Association
- belongs_to   :prototypes
- belongs_to   :comments