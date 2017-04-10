# README

## データベース定義

column = カラム名

type = データ型




## articlesテーブル


|colimn   | type      |index| null| unique|
|---------|-----------|------|-----|-------|
| title   | string    | yes  |false|       |
| body    | text      |      |false|       |
| user_id | references| yes  |false|       |

### articlesテーブルに関するアソシエーション
> belongs_to :user

> has_many : likes


### 追記
> acts as taggable on を導入して記事に対して対象言語のタグ付けを行う




## usersテーブル

| colimn  | type   | index| null| unique|
|---------|--------|------|-----|-------|


### usersテーブルに関するアソシエーション
> has_many : articles

> has_many : likes,  through: :like_users

> has_many : like_users


### 追記(gem)

> deviseのデフォルト設定を使用して、テーブルを生成する。



## like_usersテーブル

| colimn    | type       | index| null| unique|
|-----------|------------|------|-----|-------|
| like_id   | references | yes |false|       |
| user_id   | references | yes |false|       |


### like_usersテーブルに関するアソシエーション

> belongs_to :like

> belongs_to :user

## likesテーブル

| colimn    | type       | index| null| unique|
|-----------|------------|------|-----|-------|
| article_id | references | yes |false|       |



### likesテーブルに関するアソシエーション

> belongs_to :article

> belongs_to :like_users










