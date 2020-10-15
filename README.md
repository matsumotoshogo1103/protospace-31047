# テーブル設計

## users テーブル

| Column     | Type   | Option      |
| ---------- | ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| profile    | text   | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### アソシエーション

- has_many :prototypes
- has_many :comments


## prototypes テーブル

| Column     | Type       | Option      |
| ---------- | ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references |             |

### アソシエーション

- belongs_to :user
- has_many :comments



## comments テーブル

| Column    | Type       | Option      |
| --------- | ---------- | ----------- |
| text      | text       | null: false |
| user      | references |             |
| prototype | references |             |

### アソシエーション

- belongs_to :user
- belongs_to :prototype
