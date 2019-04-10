state と mutations
``` es6
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    // store.commit('increment', {amount: 10}) で state を変更する
    increment (state, payload) {
      state.count += payload.amount
    }
  }
})
```

getter (vue の算出プロパティのようなもの)
``` es6
const store = new Vuex.Store({
  state: {
    todos: [
      { id: 1, text: '...', done: true },
      { id: 2, text: '...', done: false }
    ]
  },
  getters: {
    doneTodos: state => {
      return state.todos.filter(todo => todo.done)
    },
    doneTodosCount: (state, getters) => {
      return getters.doneTodos.length
    },
    getTodoById: (state) => (id) => {
      return state.todos.find(todo => todo.id === id)
    }
  }
})
```

action
``` es6
const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  },
  actions: {
    increment (context) {
      context.commit('increment')
    },
    // `getData()` と `getOtherData()` が Promise を返すことを想定している
    async actionA ({ commit }) {
      commit('gotData', await getData())
    },
    async actionB ({ dispatch, commit }) {
      await dispatch('actionA') // `actionA` が完了するのを待機する
      commit('gotOtherData', await getOtherData())
    }
  }
})
```
