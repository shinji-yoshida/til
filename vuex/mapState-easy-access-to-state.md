``` es6
const Counter = {
  template: `<div>{{ count }}</div>`,
  computed: {
    count () {
      return this.$store.state.count
    }
  }
}
```

count を表示するために `this.$store.state.count` と書くところを、 mapState を使えば以下のように短縮できる

``` es6
const Counter = {
  computed: mapState([
    // map this.count to store.state.count
    'count'
  ])
}
```
