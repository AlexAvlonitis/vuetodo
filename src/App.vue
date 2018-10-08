<template>
  <div id="app">
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'
import './App.css'

export default {
  name: 'app',
  components: {
    TodoList
  }
}
</script>
