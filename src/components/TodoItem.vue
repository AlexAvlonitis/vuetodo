<template>
  <li>
    {{ todoItem.name }}
    <button v-on:click="removeItem(todoItem)">X</button>
  </li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todoItem'],
  methods: {
    removeItem(todoItem) {
      this.$emit('remove-item', todoItem);
    }
  }
}
</script>
