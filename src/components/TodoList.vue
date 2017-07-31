<template>
    <div class="todo-list row">
        <todo-item v-for="todo in todos" :key="todo.uid" v-bind:todo="todo"></todo-item>
    </div>
</template>

<script>
import TodoItem from './TodoItem';

export default {
  name: 'todo-list',
  props: ['todos'],
  components: {
    TodoItem,
  },
  methods: {
    addItem() {
      const newItem = {
        id: this.todos.length,
        name: `Todo Item ${this.todos.length}`,
        date: new Date(),
        completed: false,
      };
      this.todos.push(newItem);
    },
  },
};
</script>

<style>

</style>