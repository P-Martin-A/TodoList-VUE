<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add Todo">
      <input type="submit" value="Submit">
    </form>
  </div>
</template>

<script>
  import uuid from 'uuid'

  export default {
    name: 'AddTodo',
    data() {
      return {
        title: ''
      }
    },
    methods: {
      addTodo(e) {
        e.preventDefault();       

        const newTodo = {
          id: uuid.v4(),
          title: this.title,
          completed: false
        }

        this.$emit('add-todo', newTodo)

        this.title = ' '
      }
    }
  }
</script>

<style scoped>
  form{
    display: flex;
    justify-content: center;
    align-items: center;
    margin: .8rem 0;
  }

  input{
    font-size: 1.5rem;
    margin: 0 1rem;
  }

  input[type="text"]{
    padding: .5rem;
  }

  input[type="text"]:focus{
    box-shadow: 0 0 5px #66b5ff;

  }

  input[type="submit"]{
    color: white;
    padding: .8rem 1.2rem;
    background-color: #66b5ff;
    border: none;
    outline: none;
    cursor: pointer;
    border-radius: .5rem;
  }

  input[type="submit"]:hover{
    background-color: #358fe2;
    box-shadow: 0 0 5px #358fe2;
  }
</style>