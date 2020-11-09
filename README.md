# テーブル設計

## users テーブル

| Column   | Type   | Option      |
| -------- | ------ | ----------- |
| name     | string | null: false |
| email    | string | null: false |
| password | string | null: false |

### Association

- has_many :room_users
- has_many :rooms, through: room_users
- has_many :messages

## rooms テーブル

| Columu   | Type   | Option      |
| -------- | ------ | ----------- |
| name     | string | null: false |

### Association

- has_many :room_users
- has_many :rooms/ through: room_users
- has_many :messages

## room_users テーブル

| Columu   | Type       | Option                         |
| -------- | ---------- | ------------------------------ |
| user     | refarences | null: false, foreign_key: true |
| room     | refarences | null: false, foreign_key: true |

### Association

- has_many :room
- has_many :user

## messeges テーブル

| Columu   | Type       | Option                         |
| -------- | ---------- | ------------------------------ |
| content  | string     |                                |
| user     | refarences | null: false, foreign_key: true |
| room     | refarences | null: false, foreign_key: true |

### Association

- belong_to :room
- belong_to :user