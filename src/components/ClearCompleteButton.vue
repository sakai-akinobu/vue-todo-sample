<template>
  <div>
    <button @click="handleClick" :class="[{disabled: disabled}]">
      Clear completed
    </button>
  </div>
</template>

<script>
export default {
  props: {
    onClick: Function,
    disabled: Boolean,
  },
  methods: {
    handleClick(e) {
      if (this.disabled) {
        return;
      }
      this.onClick();
    },
  },
};
</script>

<style scoped>
.disabled {
  color: #aaa;
}
</style>
