<template>
  <div class="todo-item">
    <div class="todo-item__information col-md-12" v-if="!editable">
      <span class="col-md-offset-3 col-md-1">
        <input class="todo-item__completed" type="checkbox" v-model="todo.completed"/>
      </span>
      <span class="todo-item__title col-md-3">{{todo.name}}</span>
      <span class="todo-item__date col-md-2">
        <button class="todo-item__btn__edit btn" @click.prevent="startEdit()">Edit</button>
      </span>
    </div>
    <div class="todo-item__edit col-md-offset-2 col-md-10" v-if="editable">
      <div class="col-md-offset-3 col-md-3">
        <input v-model="todo.name" class="form-control" @keypress.enter="stopEdit()" @blur="cancelEdit()"/>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'todo-item',
    props: {
      todo: Object,
    },
    data() {
      return {
        editable: false,
      };
    },
    methods: {
      stopEdit() {
        this.editable = false;
      },
      startEdit() {
        this.beforeEdit = this.todo.name;
        this.editable = true;
      },
      cancelEdit() {
        this.editable = false;
        this.todo.name = this.beforeEdit;
        this.beforeEdit = '';
      },
    },
  };

</script>

<style>

</style>
