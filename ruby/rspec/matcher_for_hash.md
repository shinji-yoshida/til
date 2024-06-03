完全一致で match する場合 eq を使う
```ruby
hash = {a: 1, b: 2}
expect(hash).to eq({a: 1, b: 2})
```

部分一致の場合 include を使う
```ruby
hash = {a: 1, b: 2}
expect(hash).to include(a: 1)
```

include は nest できる
```ruby
hash = {a: {x: 1, y: 2}, b: 1}
expect(hash).to include(a: include(x: 1))
# Matcher aliases を使うと可読性が向上する
expect(hash).to include(a: a_hash_including(x: 1))
```
