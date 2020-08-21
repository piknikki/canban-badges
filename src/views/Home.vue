<template>
  <div class="home has-text-centered">
    <form @submit.prevent="addTask">
      <!--      <label for="task">Task: </label>-->
      <input
             v-model="title"
             placeholder="Add a new task"
             required
      />
        <button type="submit">
        <span class="icon"><i class="fal fa-horse-saddle"> </i> </span> Giddyup</button>
    </form>
    <br>
    <br>
    <div class="columns is-mobile is-centered">
      <div class=" column is-half box task-box is-centered">
        <Todos v-if="taskList" v-bind:taskList="taskList"></Todos>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import { v4 as uuidv4 } from 'uuid'
import Todos from '@/components/Todos'
// import axios from 'axios'  uncomment this to use the jsonplaceholder api call in methods

export default {
  name: 'Home',
  components: {
    Todos
  },
  data () {
    return {
      // newTask: '',
      title: '',
      taskList: [
        {
          id: 1,
          title: 'update the profile website regularly',
          completed: true
        },
        {
          id: 2,
          title: 'put edit button and functionality',
          completed: false
        },
        {
          id: 3,
          title: 'mood picker that uses emojis',
          completed: false
        },
        {
          id: 4,
          title: 'wall of quotes with drag and drop capability',
          completed: false
        },
        {
          id: 5,
          title: 'website for Vera\'s work',
          completed: false
        },
        {
          id: 6,
          title: 'random FontAwesome picker for no reason whatsoever',
          completed: true
        },
        {
          id: 7,
          title: 'what about revisiting Socially Awkward Gorilla?',
          completed: false
        },
        {
          id: 8,
          title: 'skills/progress bar display, maybe rainbow colors like the titles here',
          completed: true
        },
        {
          id: 9,
          title: '404 page (make it funny)',
          completed: true
        },
        {
          id: 10,
          title: 'toggle set that uses conditionals',
          completed: false
        },
        {
          id: 11,
          title: 'authentication (maybe for Socially Awkward Gorilla)',
          completed: false
        },
        {
          id: 12,
          title: 'do something with Firebase',
          completed: true
        },
        {
          id: 13,
          title: 'cookies popover',
          completed: false
        }
      ]
    }
  },
  methods: {
    addTask () {
      const newTask = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }
      // add the task to the list
      this.taskList.unshift(newTask)
      this.title = ''
    },
    removeTask: function (task) {
      this.taskList.splice(task, 1)
    },
    editTask: function (task) {
      // take out the old task
      // put in the new task -- where is the new task coming from? need input field
    }
  }
  // this will pull in a bunch of fake tasks from a jsonplaceholder website
  // created () {
  //   axios.get('https://jsonplaceholder.typicode.com/todos')
  //     .then(response => {
  //       this.taskList = response.data
  //     })
  //     .catch(err => console.log(err))
  // }
}
</script>

<style>

.table {
  margin: 0 auto;
}

.home {
  text-align: center;
}

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
