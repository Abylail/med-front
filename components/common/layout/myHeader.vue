<template>
  <header class="my-header">
    <div class="my-header__left"></div>
    <div class="my-header__center">
      <slot>{{ title }}</slot>
    </div>
    <div class="my-header__right"></div>
  </header>
</template>

<script>
export default {
  name: "myHeader",
  props: {
    title: {
      type: String,
      default: null
    }
  }
}
</script>

<style lang="scss" scoped>
.my-header {
  display: grid;
  grid-template-columns: 50px 1fr 50px;
  background: $color--primary;
  height: 50px;
  color: white;
  position: sticky;
  top: 0;
  padding: 0 $sz--hor-padding;
  font-size: $fs--title;
  line-height: 50px;
  width: calc(100% - #{2*$sz--hor-padding});

  &__center {
    text-align: center;

  }
}
</style>
