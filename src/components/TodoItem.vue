<template>
  <div>
    <h1>
      {{ todo.description }}
      {{ todo.isCompleted ? "ok" : "no" }}
    </h1>
    <button @click="deleteItem">
      Delete
    </button>
  </div>
</template>

<script>
import Todo from '../interfaces/Todo'

export default {
  name: 'TodoItem',
  props: [
    'todo'
  ],
  methods: {
    deleteItem () {
      this.$emit('delete-item', this.todo.id)
    }
  }
}
</script>
