<script setup lang="ts">
const props = defineProps(['todos'])
</script>

<template>
  <table>
    <tr>
      <th>ID</th>
      <th>Name</th>
      <th>Description</th>
      <th>Timestamp</th>
      <th>Username</th>
    </tr>
    <tr v-for="todo in todos" :key="todo.id" data-test="post">
      <td>{{ todo.id }}</td>
      <td>{{ todo.name }}</td>
      <td>{{ todo.description }}</td>
      <td>{{ todo.timestamp }}</td>
      <td>{{ todo.username }}</td>
    </tr>
  </table>
</template>
