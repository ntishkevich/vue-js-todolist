<template>
  <div class="todo-item row">
    <div class="todo-item__information col-md-12" v-if="!item.editable">
      <span class="todo-item__title col-md-8"> {{ item.title }} </span>
      <span class="todo-item__date col-md-2"> {{ item.date }} </span>
      <button class="todo-item__btn__edit btn" @click="startEdit">Edit</button>
    </div>
    <div class="todo-item__edit col-md-12" v-if="item.editable">
      <input v-model="item.title" @blur="stopEdit/>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'todo-item',
    props: {
      item: Object,
      message: String,
    },
    data() {
      return {
        item: this.props.item,
        message: this.props.message,
      };
    },
    methods: {
      stopEdit: () => {
        this.item.editable = false;
      },
      startEdit: () => {
        this.item.editable = true;
      },
    },
  };

</script>

<style>

</style>
