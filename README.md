# テーブル設計

## users テーブル

| カラム名            | 型      | バリデーション             |
| ------------------ | ------ | -----------              |
| email              | string | null: false ,unique: true|
| encrypted_password | string | null: false              |
| name               | string | null: false              |
| birth_day          |  date  | null: false              |

### アソシエーション

- has_many : booking

## booking テーブル

| カラム名               | 型         | バリデーション                  |
| ------                | ------    | -----------                   |
|user                   |references |null: false, foreign_key: true |
|shop                   |references |null: false, foreign_key: true |
|reservation_datetime   | string    |null: false                    |

### アソシエーション

- belongs_to : shop
- belongs_to : user

## shops テーブル

| カラム名               | 型          | バリデーション                  |
| ------                | ------     | -----------                   |
|store_name             | string     |null: false                    |
|telephone_number       |integer     |null: false                   |


### アソシエーション
- has_many : bookings
- has_many : campaigns

## campaigns テーブル

| カラム名         | 型           | バリデーション                   |
| ------          | ------      | -----------                    |
|title            |string       |null: false                     |
|content          | string      |null: false                     |
|start_month_id   | integer     | null: false                    |
|start_day_id     | integer     | null: false                    |
|end_month_id     | integer     | null: false                    |
|end_day_id       | integer     | null: false                    |

### アソシエーション

-belongs_to : shop