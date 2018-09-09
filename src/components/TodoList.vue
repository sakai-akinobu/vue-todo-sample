<template>
  <ul>
    <template v-for="(todo, index) in todos">
      <TodoItem :key="index" :todo="todo" :toggle-complete="toggleComplete" />
    </template>
  </ul>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
  props: {
    todos: Array,
    toggleComplete: Function,
  },
  components: {
    TodoItem,
  },
};
</script>
