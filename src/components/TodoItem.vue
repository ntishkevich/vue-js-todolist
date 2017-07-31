<template>
  <div class="todo-item row">
    <div class="todo-item__information col-md-12" v-if="!editable">
      <span class="todo-item__title col-md-offset-3 col-md-3"> {{ todo.name }} </span>
      <span class="todo-item__date col-md-2">
        <button class="todo-item__btn__edit btn" @click.prevent="startEdit">Edit</button>
      </span>
    </div>
    <div class="todo-item__edit col-md-12" v-if="editable">
      <input v-model="todo.name" @blur="stopEdit"/>
      <button class="todo-item__btn__edit btn" @click.prevent="startEdit">Save</button>
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
        this.editable = true;
      },
    },
  };

</script>

<style>

</style>
