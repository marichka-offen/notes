# vuex

mapState

**Getters** – _computed properties for stores_, result is cached based on its dependencies, and will only re-evaluate when some of its dependencies have changed. Will receive the state as their 1st argument and other getters as the 2nd argument.

```js
getters: {
    doneTodos: state => {
      return state.todos.filter(todo => todo.done)
    }

    doneTodosCount: (state, getters) => {
      return getters.doneTodos.length
    }

    getTodoById: (state) => (id) => {
      return state.todos.find(todo => todo.id === id)
    }
}

// to access getters
store.getters.doneTodosCount
store.getters.getTodoById(2)
```

`mapGetters` maps **store** getters to **local computed** properties


```js
computed: {
    ...mapGetters([
      'doneTodosCount', 
      'anotherGetter',
    ])
  }
```