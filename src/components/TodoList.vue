<template>
  <div>
    <h1>Todo List</h1>
    <ul>
      <li v-for="todoItem in todoItems" :key="todoItem.id">
        <TodoItem v-bind:name="todoItem.name"/>
      </li>
    </ul>
    <form v-on:submit='addItem'>
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
      index: 0,
      item: '',
      todoItems: []
    }
  },
  methods: {
    addItem: function(e) {
      e.preventDefault();

      this.todoItems.push({name: this.item, id: this.index});
      this.index += 1;
    }
  }
}
</script>
