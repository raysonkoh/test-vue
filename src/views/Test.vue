<template>
  <div>
    <add-todo-comp @add-todo="addTodo" />
    <div
      v-for="todo in todos"
      :key="todo.key"
    >
      <todo-item
        :todo="todo"
        @delete-item="deleteItem"
      />
    </div>
  </div>
</template>

<script >
import AddTodoComp from '../components/AddTodoComp.vue'
import TodoItem from '../components/TodoItem.vue'

export default {
  name: 'Test',
  components: { TodoItem, AddTodoComp },
  data () {
    return {
      todos: [{
        id: 1,
        description: 'this is test description',
        isCompleted: false
      }, {
        id: 2,
        description: 'this is test description 2',
        isCompleted: true
      }]
    }
  },
  methods: {
    addTodo (newTodo) {
      this.todos = [...this.todos, newTodo]
    },
    deleteItem (id) {
      this.todos = this.todos.filter(t => t.id !== id)
    }
  }
}
</script>
