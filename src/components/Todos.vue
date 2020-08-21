<template>
  <table class="table is-striped is-hoverable is-narrow">
    <thead>
    <tr>
      <th>Task</th>
      <th>Done</th>
      <th>Delete</th>
<!--      <th>Edit</th>-->
    </tr>
    </thead>
    <tbody>
    <tr v-for="task in taskList" :key="task.id">
      <td :class="{'is-complete':task.completed}">{{ task.title }}
      </td>
      <td>
        <button @click="markComplete(task)">
          <span class="icon">
            <i class="fal fa-badge-check"></i>
          </span></button>
      </td>

      <td>
        <button @click="removeTask(task.id)">
          <span class="icon"><i class="fal fa-space-station-moon-alt"></i></span></button>
      </td>
<!--      <td>-->
<!--        <button @click="editTask(task)">-->
<!--          <span class="icon"><i class="fal fa-jedi"></i></span></button>-->
<!--      </td>-->
    </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: 'todos',
  props: ['taskList'],
  methods: {
    addTask () {
      // add the task to the list
      this.taskList.push(this.newTask)
      this.newTask = ''
    },
    markComplete (task) {
      // <i class="fad fa-badge-check"></i> todo: change to this badge when complete
      task.completed = !task.completed
    },
    removeTask: function (id) {
      // this.taskList.splice(task, 1) different way to do it, by passing the task instead of the id
      this.taskList = this.taskList.filter(task => task.id !== id)
    },
    editTask: function (task) {
      // take out the old task
      // put in the new task -- where is the new task coming from? need input field
    }
  }
}
</script>

<style scoped>
.is-complete {
  text-decoration: line-through;
}

</style>
