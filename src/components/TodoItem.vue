<template>
  <div>
    {{ name }}
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    name: String
  },
}
</script>
