<template>
    <div>
        <span class="title">To do:</span>
        <task-list :tasks="tasks" @done="onTaskDone" @remove="onTaskRemove"></task-list>
        <hr>
        <save-task @created="onNewTaskCreated"></save-task>
    </div>
</template>

<script>
import TaskList from './TaskList.vue'
import SaveTask from './SaveTask.vue'

export default {
  components: {
    TaskList,
    SaveTask
  },
  data() {
      return {
          tasks: [
              {
                  title: 'Wake up'
              },
              {
                  title: 'Eat breakfast'
              },
              {
                  title: 'Go to work'
              }
          ],
          doneTasks: []
      }
  },
  methods: {
      onNewTaskCreated (value) {
          this.tasks.push(value)
      },
      onTaskDone (value) {
          let doneTask = this.tasks.splice(value, 1);
          this.doneTasks.push(doneTask);
      },
      onTaskRemove (value) {
          this.tasks.splice(value, 1);
      }
  }
}
</script>

<style>
    div {
        background-color: #eaeaea;
        padding: 10px;
    }
    .title {
        font-size: 30px;
    } 
</style>