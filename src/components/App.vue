<template>
  <div>
    <Input :value="input" :onChange="changeInput" :onEnter="addTodo" />
    <TodoList :todos="todos" :toggleComplete="toggleComplete" />
  </div>
</template>

<script>
import Input from './Input.vue';
import TodoList from './TodoList.vue';

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
  },
  components: {
    Input,
    TodoList,
  },
};
</script>
