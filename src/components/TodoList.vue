<template>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.value }}
      <button type="button" @click="$emit('remove', todo.id)">&times;</button>
    </li>
  </ul>
</template>

<script setup>
import { defineProps, toRef } from 'vue'

const props = defineProps(['todos'])
const todos = toRef(props, 'todos')
</script>
