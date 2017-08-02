<template>
  <div class="todo-list row">
    <div class="new-item col-md-offset-2 col-md-10">
      <div class="col-md-offset-3 col-md-3">
        <input class="form-control" v-model="newTodo" @keypress.enter="addTodo()">
      </div>
    </div>
    <div class="todo-items col-md-12">
      <todo-item v-for="todo in todos" :key="todo.uid" :todo="todo"></todo-item>
    </div>
  </div>

</template>

<script>
import TodoItem from './TodoItem';

export default {
  name: 'todo-list',
  props: {
    todos: Array,
  },
  components: {
    TodoItem,
  },
  data() {
    return {
      newTodo: '',
    };
  },
  methods: {
    addTodo() {
      const newItem = {
        id: this.todos.length,
        name: this.newTodo.trim(),
        date: new Date(),
        completed: false,
      };
      this.todos.push(newItem);
      this.newTodo = '';
    },
  },
};
</script>

<style>

</style>
