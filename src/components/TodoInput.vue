<template>
  <form @submit.prevent="save">
    <label>
      <input v-model="todo" />
      <button>OK</button>
    </label>
  </form>
</template>

<script setup>
import { defineEmit, ref } from 'vue'
const todo = ref('')

const emit = defineEmit(['add'])

const save = () => {
  emit('add', todo.value)
  todo.value = ''
}
</script>
