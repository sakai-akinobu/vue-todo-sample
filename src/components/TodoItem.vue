<template>
  <div v-bind:class="{completed: todo.completed}" @click="handleClick">
    <input type="checkbox" :checked="todo.completed" />
    <span>{{ todo.title }}</span>
  </div>
</template>

<script>
export default {
  props: {
    todo: Object,
    toggleComplete: Function,
  },
  methods: {
    handleClick(e) {
      this.toggleComplete(this.todo);
    },
  },
};
</script>

<style scoped>
.todo {
  cursor: pointer;
}

.completed {
  color: #aaa;
  text-decoration: line-through;
}
</style>
