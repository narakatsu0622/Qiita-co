# README

## データベース定義

column = カラム名

type = データ型




## articlesテーブル


|colimn   | type      |index| null| unique|
|---------|-----------|------|-----|-------|
| title   | string    | yes  |false|       |
| language | string    |      |false|       |
| body    | text      |      |false|       |
| user_id | references| yes  |false|       |

###articlesテーブルに関するアソシエーション
> belongs_to :user
> has_many :cheers through: :cheer_users
> has_many :cheer_users




## usersテーブル

| colimn  | type   | index| null| unique|
|---------|--------|------|-----|-------|


### usersテーブルに関するアソシエーション
> has_many : articles
> has_many : cheers through: :cheer_users
> has_many : cheer_users
### 追記(gem)

> deviseのデフォルト設定を使用して、テーブルを生成する。



## cheersテーブル

| colimn    | type       | index| null| unique|
|-----------|------------|------|-----|-------|


###cheersテーブルに関するアソシエーション

> belongs_to :article
> belongs_to :user





## article_usersテーブル


| colimn    | type       | index| null| unique|
|-----------|------------|------|-----|-------|
| article_id| references | yes |false|       |
| user_id   | references | yes |false|       |

### group_usersテーブルに関するアソシエーション

> belongs_to : article
> belongs_to : user
