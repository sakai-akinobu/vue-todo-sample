<template>
  <input
    :value="value"
    @input="handleInput"
    @keyup.enter="handleEnter"
    placeholder="What needs to be done?"
    class="input"
  />
</template>

<script>
export default {
  props: {
    value: String,
    onChange: Function,
    onEnter: Function,
  },
  methods: {
    handleInput(e) {
      this.onChange(e.target.value);
    },
    handleEnter(e) {
      this.onEnter(e.target.value);
    },
  },
};
</script>

<style scoped>
.input {
  width: 300px;
  font-size: 1.2em;
}
</style>
