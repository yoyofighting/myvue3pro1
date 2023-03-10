# myvue3pro1
与vue2项目的区别是 使用了v-model进行了复杂数据类型的双向绑定 动态样式
遇到的一些bug
1.import TodoList from './components/todo-list/TodoList.vue'
// import TodoList from '@/components/todo-list/TodoList.vue'这是错的
2.TodoButton.vue中emits: ['update:active'],
// 当时写成['update: active'],多了个空格就不出效果？
  
