<template>
  <ul>
    <template v-for="(todo, index) in todos">
      <Todo :key="index" :todo="todo" :toggle-complete="toggleComplete" />
    </template>
  </ul>
</template>

<script>
import todo from './todo.vue';

export default {
  props: {
    todos: Array,
    toggleComplete: Function,
  },
  components: {
    Todo: todo,
  },
};
</script>
