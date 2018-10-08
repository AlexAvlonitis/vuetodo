<template>
  <div>
    <li v-show="!isEditing">
      {{ todoItem.name }}
      <button v-on:click="removeItem(todoItem)">X</button>
      <button v-on:click="openForm">Edit</button>
    </li>
    <form v-show="isEditing" v-on:submit.prevent="closeForm">
      <input v-model="todoItem.name" />
    </form>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todoItem'],
  data: function() {
    return {
      isEditing: false
    }
  },
  methods: {
    removeItem(todoItem) {
      this.$emit('remove-item', todoItem);
    },
    openForm() {
      this.isEditing = true
    },
    closeForm() {
      this.isEditing = false
    }
  }
}
</script>
