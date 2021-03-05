<template>
  <div>
    <p>
      新しくTODOを作成する：
      <input v-model="text" type="text" />
      <input type="submit" @click="pushTodo" />
    </p>
    <ul v-for="todo in todos" :key="todo.id">
      <li>{{ todo }} <button @click="deleteTodo(todo)">完了</button></li>
    </ul>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
interface DataInterFace {
  text: string
  todos: string[]
}

export default Vue.extend({
  data(): DataInterFace {
    return {
      text: '',
      todos: [],
    }
  },
  watch: {
    todos: {
      handler() {
        localStorage.setItem('todos', this.todos.toString())
      },
    },
  },
  mounted() {
    const todos = localStorage.getItem('todos')
    if (!todos) return
    this.todos = todos.split(',')
  },
  methods: {
    pushTodo() {
      if (!this.text) return
      this.todos.push(this.text)
      this.text = ''
    },
    deleteTodo(target: string) {
      this.todos = this.todos.filter((todo) => todo !== target)
    },
  },
})
</script>
