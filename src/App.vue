<template>
  <section id="app">
    <img src="./assets/logo.png"/>
    <todo-list v-bind:todos="todos"></todo-list>
  </section>
</template>

<script>
import TodoList from './components/TodoList';

export default {
  name: 'app',
  components: {
    TodoList,
  },
  data() {
    const todoList = [];
    for (let i = 0; i < 10; i += 1) {
      todoList.push({
        uid: i + 1,
        name: `Todo Item ${i + 1}`,
        date: new Date(),
        completed: false,
      });
    }

    return {
      todos: todoList,
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
