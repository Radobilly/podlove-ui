<template>
  <div class="input-group" :class="{ [`elements-${elements}`]: true }">
    <slot name="button" />
    <slot name="input" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      elements: 0
    }
  },

  mounted() {
    this.elements = this.$el.children.length
  }
}
</script>

<style lang="scss" scoped>
@import 'boot';
@import 'tokens/defaults';
@import 'tokens/input';

.input-group {
  box-sizing: border-box;
  display: flex;

  .input-text,
  .input-select {
    padding: $padding / 2;
    width: 100%;
    border-radius: 0 3px 3px 0;
    border-width: 1px 1px 1px 0;
    height: $input-height;
  }

  .button {
    width: $addon-button-width;
    display: block;
    border-width: 1px;
    border-radius: 3px 0 0 3px;
    height: $input-height;
  }

  &.elements-2 {
    *:nth-child(1) {
      width: auto;
      border-radius: 3px 0 0 3px;
    }
  }

  &.elements-3 {
    *:nth-child(1) {
      width: auto;
      border-radius: 3px 0 0 3px;
    }

    *:nth-child(2) {
      width: auto;
      border-radius: 0;
    }
  }
}
</style>
