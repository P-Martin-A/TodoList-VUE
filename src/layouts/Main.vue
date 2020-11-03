<template>
  <main>
    <AddTodo @add-todo="addTodo" />
    <Todos :todos="todos" @delete-todo="deleteTodo" />
  </main>
</template>

<script>
  import AddTodo from '../components/AddTodo'
  import Todos from '../components/Todo'

  export default {
    name: 'Main',
    components: {
      AddTodo,
      Todos,
    },
    data() {
      return {
        todos: [
          {
            id: 1,
            title: 'Todo One',
            completed: false
          },
          {
            id: 2,
            title: 'Todo Two',
            completed: false
          },
          {
            id: 3,
            title: 'Todo Three',
            completed: false
          },
          {
            id: 4,
            title: 'Todo Four',
            completed: false
          },
          {
            id: 5,
            title: 'Todo Five',
            completed: false
          }
        ]
      }
    },
    methods: {
      deleteTodo(id) {
        this.todos = this.todos.filter(todo => todo.id !== id)
      },
      addTodo(newTodo) {
        this.todos = [...this.todos, newTodo]
      }
    }
  }
</script>
