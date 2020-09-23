# docker-rails

## 手順

1: docker-compose runでアプリケーションを作成する
```
docker-compose run web rails new . --force --no-deps --database=postgresql
```
2: docker-compose buildでイメージを作成
```
docker-compose build
```
3: config/database.ymlの内容を更新する
```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: harumax
  password: haruyuki0815 # docker-compose.ymlのPOSTGRES_PASSWORDで指定した値
  pool: 5
```
4: データベースの作成
```
docker-compose run web rails db:create
```
5: 起動
```
docker-compose up
```
