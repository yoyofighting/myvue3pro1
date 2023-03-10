<template>
<div>
  <TodoInput @add="onAddNewTask"></TodoInput>
  <TodoList :list="tasklist"></TodoList>
  <TodoButton v-model:active="activeBtnIndex"></TodoButton>
</div>
</template>

<script>
import TodoList from './components/todo-list/TodoList.vue'
// import TodoList from '@/components/todo-list/TodoList.vue'这是错的
import TodoInput from './components/todo-input/TodoInput.vue'
import TodoButton from './components/todo-button/TodoButton.vue'

export default {
  name: 'MyApp',
  data() {
    return {
      todolist: [
        {id:1, task: '学习html', done :false},
        {id:2, task: '学习css', done :false},
        {id:3, task: '学习javascript', done :false}
      ],
      nextId: 4,
      activeBtnIndex: 0
    }
  },
  components: {
    TodoList,
    TodoInput,
    TodoButton
  },
  methods: {
    onAddNewTask(taskname) {
      this.todolist.push({
        id: this.nextId,
        task: taskname,
        done: false
      })
      this.nextId++
    }
  },
  computed: {
    tasklist() {
      switch(this.activeBtnIndex) {
        case 0:
          return this.todolist
        case 1:
          return this.todolist.filter(x => x.done === true)
        case 2:
          return this.todolist.filter(x => x.done !== true)
      }
    }
  } 
}
</script>
<style lang="less" scoped>
</style>
