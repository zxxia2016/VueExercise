<template>
  <div id="app">
    <div class="todo-container">
      <div class="todo-wrap">
        <Header :AddTodoItem="AddTodoItem" />
        <List :list=" list" />
        <Footer :list=" list" :selectAll="selectAll" :removeFinishedItems="removeFinishedItems" />
      </div>
    </div>
  </div>
</template>

<script>
import Header from './TodoList/Header.vue'
import List from './TodoList/List.vue'
import Footer from './TodoList/Footer.vue'
export default {
  name: 'App',
  components: {
    Header,
    List,
    Footer
  },
  data () {
    return {
      list: [
        { finished: false, title: 'xxxx' },
        { finished: false, title: 'yyyy' },
        { finished: false, title: 'zzzz' }
      ]
    }
  },
  methods: { 
    AddTodoItem (title) {
      this.list.push({ title: title, finished: false })
    },
    selectAll (value) {
      this.list.forEach(todo => {
        todo.finished = value
      })
    },
    removeFinishedItems () {
      this.list = this.list.filter(todo => !todo.finished)
    }
  }
}
</script>

<style>

.todo-container {
  width:600px;
  margin:0 auto;
}

.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

</style>
