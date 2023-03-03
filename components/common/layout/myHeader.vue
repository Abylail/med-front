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

<style scoped>

</style>
