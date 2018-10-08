<template>
  <div>
    <h1>Todo List</h1>
    <ul>
      <TodoItem
        v-for="(todoItem, index) in todoItems"
        v-bind:todoItem="todoItem"
        v-bind:key="index"
        v-on:remove-item="removeItem"
      />
    </ul>
    <form v-on:submit.prevent='addItem'>
      <input type='text' placeholder="Add task" v-model='item' />
      <br />
      <input type='submit' value="Add" />
    </form>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  name: 'TodoList',
  components: {
    TodoItem
  },
  data: function() {
    return {
      item: '',
      todoItems: []
    }
  },
  methods: {
    addItem() {
      this.todoItems.push({name: this.item});
      this.item = '';
    },
    removeItem(todoItem) {
      const todoIndex = this.todoItems.indexOf(todoItem);
      this.todoItems.splice(todoIndex, 1);
    }
  }
}
</script>
