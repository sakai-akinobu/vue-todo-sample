<template>
  <ul>
    <template v-for="(todo, index) in todos">
      <Todo :key="index" :todo="todo" :toggle-complete="toggleComplete" />
    </template>
  </ul>
</template>

<script>
import Todo from './Todo.vue';

export default {
  props: {
    todos: Array,
    toggleComplete: Function,
  },
  components: {
    Todo,
  },
};
</script>
