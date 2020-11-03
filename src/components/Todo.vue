<template>
  <div>
    <ul>
      <li v-for="todo of todos" :key="todo.id">
          <TodoItem :todo="todo" @delete-todo="$emit('delete-todo', todo.id)"/>
      </li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem'

export default {
  name: 'Todos',
  components: {
    TodoItem
  },
  props: [ 
    'todos'
  ]
}
</script>

<style scoped>

</style>