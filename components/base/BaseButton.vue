<template>
  <button class="base-button" :class="[{'base-button--full-width': fullWidth}]" v-on="$listeners">
    <slot/>
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  props: {
    fullWidth: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss" scoped>
.base-button {
  background: $color--primary;
  color: white;
  border-radius: 6px;
  padding: 16px;
  border: none;
  transition: .15s;

  &--full-width {
    width: 100%;
  }

  &:active {
    opacity: .7;
  }
}
</style>
