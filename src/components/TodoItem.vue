<template>
  <div class="todo-item">
    <div>
      <input type="checkbox" @change="markComplete">
      <h4 :class="{'is-complete' : todo.completed}" v-text="todo.title"></h4>
    </div>
    <button class="delete" @click="$emit('delete-todo', todo.id)">X</button>
  </div>
</template>

<script>
  export default {
    name: 'TodoItem',
    props: [
      'todo',
    ],
    methods: {
      markComplete() {
        this.todo.completed = !this.todo.completed
      }
    }
  }
</script>

<style scoped>
  .todo-item{
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: #f4f4f4;
    padding: .8rem;
    border: 1px solid #cecece;
  }

  .todo-item div{
    display: flex;    
    align-items: center;
  }

  .todo-item div h4{
    font-size: 1.2rem;
  }

  .todo-item div h4.is-complete{
    text-decoration: line-through;
    text-decoration-color: #f02d2d;
  }

  .todo-item div input{
    margin-right: .5rem;
  }

  .todo-item .delete{
    border-radius: 50%;
    background-color: #f02d2d;
    padding: .5rem;
    border: none;
    outline: none;
    color: white;
    cursor: pointer;
  }

  .todo-item .delete:hover{
    background-color: #d62828;
  }
</style>