# ダンプ
pg_dump はアーカイブ形式でもダンプできる。　`-F` オプションでアーカイブ形式になる。
```
$ pg_dump -Fc database名 > backup_file名
```
* -cはcustom形式を表す。-tとするとtar形式になる

# リストア
```
$ pg_restore -C -d postgres バックアップファイル名
```
* -C オプションを付けるとリストア前にデータベースを作成
* -d オプションはデータベース名を指定
