# MongoDBとは
ドキュメント指向（Document-Oriented）のNoSQLデータベース。
RDBのように行と列でデータを管理するのではなく、Binary JSON形式でデータを保存・管理する。
データベース、コレクション（RDBでいうテーブル）、ドキュメント（RDBでいうレコード）

## ポート
27017

## デフォルトデータベース
ace

## 接続方法
```bash
mongo <ターゲット>:<ポート>
mongo -p -u <ユーザー名> <データベース名> # ユーザー名、パスワードとデータベース名を指定して接続
mongo --port <ポート> <データベース名> --eval "db.<コレクション名>.find().forEach(printjson)"; # 接続と同時にすべてのコレクションを表示
mongo --port <ポート> <データベース名> --eval 'db.<コレクション名>.update({"_id":ObjectId("<オブジェクトのID>")},{$set:{"<キー>":"<値>"}}) # 接続と同時にデータを挿入(ObjectIdを指定)
```

## コマンド
```bash
show dbs # すべてのデータベースを表示
use <データベース> # データベースを切り替え
show collections # コレクションを表示
db.<コレクション名>.find().forEach(printjson) # json形式でデータを表示
db.<コレクション名>.insert({"<キー>":"<値>"}) # データを挿入
```
