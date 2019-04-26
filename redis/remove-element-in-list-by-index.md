直接リストの index を指定して削除する方法はないので、
index を指定して value を書き換えた後で value に一致する要素を削除する。

```
@redis.lset("#{@namespace}/#{specified_queue}", index, "DELETED")
@redis.lrem("#{@namespace}/#{specified_queue}", 1, "DELETED")
```

https://stackoverflow.com/questions/31580535/remove-element-at-specific-index-from-redis-list
