<template>
  <div>
    <p>
      新しくTODOを作成する：
      <input v-model="text" type="text" />
      <input type="submit" @click="pushTodo" />
    </p>
    <ul v-for="todo in todos" :key="todo.id">
      <li>{{ todo }} <button>完了</button></li>
    </ul>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      text: '',
      todos: [],
    }
  },
  methods: {
    pushTodo() {
      if (!this.text) return
      this.todos.push(this.text)
      this.text = ''
    },
  },
})
</script>
