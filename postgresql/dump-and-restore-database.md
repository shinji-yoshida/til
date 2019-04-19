# ダンプ
``` bash
$ PGPASSWORD=password pg_dump -U user -d database > ~/dump/dumpfile.sql
```

# リストア
``` bash
$ # database削除
$ PGPASSWORD=password dropdb -U user database
$ # database作成
$ PGPASSWORD=password createdb -U user database
$ # リストア
$ PGPASSWORD=password psql -U user database < ~/dump/dumpfile.sql
```
database を空にしておかないとリストア時にいろいろ重複してうまくいかない。

(https://qiita.com/gakkie/items/a99a4dcda3c2d0a445a3)
