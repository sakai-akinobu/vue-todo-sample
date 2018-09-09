<template>
  <div>
    <h1>Vue Todo list sample</h1>
    <Input :value="input" :onChange="changeInput" :onEnter="addTodo" />
    <TodoList :todos="todos" :toggleComplete="toggleComplete" />
    <ClearCompleteButton :onClick="clearComplete" :disabled="!hasComplete" />
  </div>
</template>

<script>
import Input from './Input.vue';
import TodoList from './TodoList.vue';
import ClearCompleteButton from './ClearCompleteButton.vue';

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
      this.todos.unshift({
        title,
        completed: false,
      });
      this.input = '';
    },
    toggleComplete(todo) {
      todo.completed = !todo.completed;
    },
    clearComplete() {
      this.todos = this.todos.filter(todo => !todo.completed);
    },
  },
  computed: {
    hasComplete() {
      return this.todos.some(todo => todo.completed);
    },
  },
  components: {
    Input,
    TodoList,
    ClearCompleteButton,
  },
};
</script>
