<template>
  <div class="todo-item row">
    <div class="todo-item__information col-md-12" v-if="!editable">
      <span class="todo-item__title col-md-offset-3 col-md-4"> {{ `${todo.name} ${todo.date}` }} </span>
      <span class="todo-item__date col-md-3">
        <button class="todo-item__btn__edit btn" @click="startEdit">Edit</button>
      </span>
    </div>
    <div class="todo-item__edit col-md-12" v-if="editable">
      <input v-model="todo.name" @blur="stopEdit"/>
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
      stopEdit: () => {
        this.data().todo.editable = false;
      },
      startEdit: () => {
        // eslint-disable-next-line
        console.log(this);
        this.data().todo.editable = true;
      },
    },
  };

</script>

<style>

</style>
