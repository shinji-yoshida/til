``` es6
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  },
  created: function () {
    // ライフサイクルフック
    // その他のフックは https://jp.vuejs.org/v2/guide/instance.html を参照
    // `this` は vm インスタンスを指します
    console.log('a is: ' + this.a)
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  },
  computed: {
    // 算出 getter 関数
    reversedMessage: function () {
      return this.message.split('').reverse().join('')
    },
    fullName: {
      // getter 関数
      get: function () {
        return this.firstName + ' ' + this.lastName
      },
      // setter 関数
      set: function (newValue) {
        var names = newValue.split(' ')
        this.firstName = names[0]
        this.lastName = names[names.length - 1]
      }
    }
  },
  watch: {
  // 監視プロパティ(watched property)
    messagePrefix: function (val) {
      this.message = val + this.message
    }
  }
})

var component = Vue.component('todo-item', {
  // todo-item コンポーネントはカスタム属性のような "プロパティ" で受け取ります。
  // このプロパティは todo と呼ばれます。
  props: ['todo'],
  data: function () { // component の data は関数でなければならない
    return {
      count: 0
    }
  },
  template: '<li>{{ todo.text }}</li>'
})
```
