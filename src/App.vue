<template>
  <div>
    <todo-input @add="addTodo" />
    <todo-list @remove="removeTodo" :todos="todos" />
  </div>
</template>

<script setup>
import { defineComponent, ref } from 'vue'

import TodoInput from '@/components/TodoInput'
import TodoList from '@/components/TodoList'

defineComponent({
  TodoInput,
  TodoList
})

const todos = ref([])
const addTodo = (todo) => {
  todos.value.push({
    id: todos.value.length,
    value: todo
  })
}
const removeTodo = (id) => {
  todos.value.splice(id, 1)
}
</script>
