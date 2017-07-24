<template>
  <div class="dropdown customSelect">
    <ul class="dropdown-menu">
      <li v-for="(option, index) in options" :key="index">
        <a v-on:mousedown.prevent="select(option)">
          {{ displayTextConte(option) }}
        </a>
      </li>
      <li v-if="!options.length">

      </li>
    </ul>
  </div>
</template>

<script>
  const todoItem = new Vue();

</script>

<style>

</style>
