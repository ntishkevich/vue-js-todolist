<template>
  <section id="app">
    <img src="./assets/logo.png">
    <todo-item v-for="todo in todos" :key="todo.uid" :todo="todo"></todo-item>
  </section>
</template>

<script>
import TodoItem from './components/TodoItem';

export default {
  name: 'app',
  components: {
    TodoItem,
  },
  data() {
    const item = {
      uid: 1,
      name: 'Todo Item 1',
      date: new Date(),
      completed: false,
    };
    return {
      todos: [item],
      message: 'Hello World',
    };
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
