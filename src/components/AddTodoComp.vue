<template>
  <div>
    <h1>This is add todo comp </h1>
    <input
      v-model="description"
      type="text"
      value="description"
      placeholder="task description"
    >
    <button
      type="submit"
      @click="addTodo"
    >
      Submit
    </button>
  </div>
</template>

<script>
export default {
  name: 'AddTodoComp',
  data () {
    return {
      description: ''
    }
  },
  methods: {
    addTodo (e) {
      e.preventDefault()
      const newTodo = {
        id: 123,
        description: this.description,
        isCompleted: false
      }

      this.$emit('add-todo', newTodo)
      this.description = ''
    }
  }
}
</script>
