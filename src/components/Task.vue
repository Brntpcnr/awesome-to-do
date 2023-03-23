<template>
  <li> <!-- index element makes it so that for example we put a delete button next to each task, with index we are able to assign a button to that task -->
    <div> <slot></slot> {{ index }}</div> <!-- slot is one of the other methods to pass data, like props  -->
    <small> {{ task.dueDate }} @ {{ task.dueTime }}</small>
    <button @click="deleteTask(index)">X</button>
  </li>
</template>

<script>
  export default {
    props: ['task', 'index']     //now we import the props from the index.vue page
  }
</script>

<style>

</style>
