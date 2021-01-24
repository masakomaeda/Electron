## PostgreSQLをインストール
```
sudo apt install postgresql postgresql-contrib
```
Postgresロールに関連付けられたpostgresというユーザーアカウントが作成される  
まずはこのユーザーにパスワードをつけてやる  
```
sudo passwd postgres
```
peer認証だとOSユーザーでないとろぐいんできなくなっちまうのでmd5に設定をかえる
```
sudo vi /etc/postgresql/12/main/pg_hba.conf

#local all all peer
local all all md5
```
一瞬postgresユーザーになる  
```
sudo -i -u postgres
```
DBを作る  
```
createdb 好きなDB名（例:createdb masaodb)
```
utuntuのloginユーザーにpostgresの今作ったDBへログイン権限を与える
```
postgres@UBU:~$ psql masaodb
psql (12.5 (Ubuntu 12.5-0ubuntu0.20.04.1))
Type "help" for help.

masaodb=# create role ubuntuログインユーザー名 with login;
CREATE ROLE
masaodb=# \q
postgres@UBU2~$
```
ユーザー（ロール）を追加する。
```
create role ユーザー名 with LOGIN password 'パスワード';
```
指定したユーザーでログインするには以下。
```
psql -U ユーザー名 -d ｄｂ名
```
スキーマ作ってテーブル作る
```
create schema スキーマ名 authorization 持ち主ユーザー名;
\dn ←スキーマ一覧確認できる
select current_schema();　←今いるスキーマを確認できる
```

