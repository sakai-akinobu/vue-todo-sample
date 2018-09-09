<template>
  <div>
    <Input :value="input" :onChange="changeInput" :onEnter="addTodo" />
  </div>
</template>

<script>
import input from './input.vue';

export default {
  data() {
    return {
      input: '',
      todos: [],
    };
  },
  methods: {
    changeInput(value) {
      this.input = value;
    },
    addTodo(title) {
      this.todos.push({
        title,
        completed: false,
      });
      this.input = '';
    }
  },
  components: {
    Input: input,
  },
};
</script>
