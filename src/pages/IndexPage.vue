<template>
  <q-page padding>
    <ul>
      <task
      v-for="(task, index) in tasks"
      :key="task.id"
      :task="task"
      :index="index">{{ task.name }}</task>           <!-- to use the task component we imported we create an html element, now we need to pass tasks from the index.vue(page component) into the task(child component)   -->
    </ul>                              <!-- to pass data from parent component to child component we will use props, :task="" is our prop in this case -->
  </q-page>
</template>

<script>
export default {
    data () {
      return {
        tasks:[
          {
            id: 1,
            name:'Go to shop',
            dueDate: '12/04/2023',
            dueTime: '18:30'
          },
          {
            id: 2,
            name:'Get bananas',
            dueDate: '13/04/2023',
            dueTime: '16:30'
          },
          {
            id: 3,
            name:'Get apples',
            dueDate: '13/04/2023',
            dueTime: '17:00'
          }
        ]
      }
    },
    methods :{
      deleteTask(index) {
        this.tasks.splice(index, 1)  //splice basically means delete, 1 means that one task at a time will be deleted
      }
    },
    components: {   //quick way to import from another page, in this case we are importing child components. We specify the name of the component as task, as it can be seen below
      'task' : require('components/Task.vue').default
    }
 }
</script>

<style>

</style>
