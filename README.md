# README

<!-- usersテーブル -->
| Column             | Type   | Options                   |
|                    |        |                           |
| email              | string | null: false ,unique: true |
| encrypted_password | string | null: false               |

### Association
has_many :items
has_many :orders

<!-- itemsテーブル -->
| Column           | Type       | Options                       |
|                  |            |                               |
| item             | string     | null: false                   |
| item_text        | text       | null: false                   |
| situation_id     | integer    | null: false                   |
| freshness_id     | integer    | null: false                   |
| price            | string     | null: false                   |
| user             | references | null: false,foreign_key: true |

### Association
belongs_to :user
has_one :order


<!-- ordersテーブル -->
| Column           | Type       | Options                       |
|                  |            |                               |
| telephone        | string     | null: false                   |
| situation_id     | integer    | null: false                   |
| item             | references | null: false,foreign_key: true |
| user             | references | null: false,foreign_key: true |

### Association
belongs_to :item
belongs_to :user

