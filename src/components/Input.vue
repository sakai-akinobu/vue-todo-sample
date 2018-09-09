<template>
  <input :value="value" @input="handleInput" @keyup.enter="handleEnter" />
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
    }
  },
};
</script>
