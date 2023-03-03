<template>
  <div class="default-layout">
    <Nuxt/>

    <my-bottom-bar/>
  </div>
</template>

<script>
import MyBottomBar from "~/components/common/layout/myBottomBar.vue";

export default {
  name: "default",
  components: {MyBottomBar}
}
</script>

<style lang="scss" scoped>
.default-layout {
  //min-height: 100vh;
}
</style>
