<template>
  <div class="home">
    <div class="container">
    <form @submit.prevent="addTask">
<!--      <label for="task">Task: </label>-->
      <input
             v-model="newTask"
             placeholder="Add a new task"
             required
      />
        <button type="submit">
        <span class="icon"><i class="fal fa-horse-saddle"> </i> </span> Giddyup</button>
    </form>
    <br>
    <br>
      <div class="container box">
        <table class="table is-striped is-hoverable is-narrow">
          <thead>
            <tr>
              <th>Task</th>
              <th>Delete</th>
              <th>Edit</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(task, index) in taskList" :key="index">
              <td>{{ task }}
              </td>
              <td>
                <button @click="removeTask(task)">
                  <span class="icon"><i class="fal fa-space-station-moon-alt"> </i> </span></button>
              </td>
              <td>
                <button @click="editTask(task)">
                  <span class="icon"><i class="fal fa-jedi"></i> </span></button>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  data () {
    return {
      newTask: '',
      taskList: [
        'do one thing',
        'do another thing'
      ]
    }
  },
  methods: {
    addTask () {
      // add the task to the list
      this.taskList.push(this.newTask)
      this.newTask = ''
    },
    removeTask: function (task) {
      this.taskList.splice(task, 1)
    },
    editTask: function (task) {
      // take out the old task
      // put in the new task -- where is the new task coming from? need input field
    }
  }
}
</script>

<style>
  input, button {
    line-height: 2;
    font-size: large;
  }

  button {
    margin: 10px;
  }

  i {
    padding: 0 5px;
  }
</style>
