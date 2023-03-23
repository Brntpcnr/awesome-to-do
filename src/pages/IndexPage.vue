<template>
  <q-page padding>
    <ul>
      <li v-for="(task, index) in tasks"> <!-- index makes it so that for example we put a delete button next to each task, with index we are able to assign a button to that task -->
        <div> {{ task.name }} {{ index }}</div>
        <small> {{ task.dueDate }} @ {{ task.dueTime }}</small>
        <button @click="deleteTask(index)">X</button>
      </li>
    </ul>
  </q-page>
</template>

<script>
export default {
    data () {
      return {
        tasks:[
          {
            name:'Go to shop',
            dueDate: '12/04/2023',
            dueTime: '18:30'
          },
          {
            name:'Get bananas',
            dueDate: '13/04/2023',
            dueTime: '16:30'
          },{
            name:'Get apples',
            dueDate: '13/04/2023',
            dueTime: '17:00'
          }
        ]
      }
    },
    methods :{
      deleteTask(index) {
        this.tasks.splice(index, 1) //splice basically means delete, 1 means that one task at a time will be deleted
      }
    }
 }
</script>

<style>

</style>
