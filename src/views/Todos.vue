<script setup lang="ts">
import Todos from '../components/Todos.vue'
</script>

<template>
  <div class="page">
    <h2>Todos</h2>
    <Todos :todos="todos" />
  </div>
</template>

<style lang="scss" scoped>
.page {
  padding: 5px;
}
</style>

<script lang="ts">
import axios from 'axios'

export default {
  data() {
    return {
      todos: null
    }
  },
  methods: {
    async getTodos() {
      let r = await axios.get('http://localhost:3000/todos')
      this.todos = r.data
    }
  },
  beforeMount() {
    this.getTodos()
  }
}
</script>
