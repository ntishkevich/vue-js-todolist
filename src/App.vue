<template>
  <div id="app">
    <img src="./assets/logo.png">
    <!--<hello></hello>-->
    <todo-item :item="item" :message="message"></todo-item>
  </div>
</template>

<script>
// import Hello from './components/Hello';
import TodoItem from './components/TodoItem';

export default {
  name: 'app',
  components: {
//    Hello,
    TodoItem,
  },
  data() {
    const item = {
      title: 'Todo Item 1',
      date: new Date(),
      completed: false,
      editable: false,
    };
    return {
      item,
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
