<template>
  <footer class="my-bottom-bar">
    <div class="my-bottom-bar__item"
         :class="{'selected': module.code === selectedModuleCode}"
         v-for="module in list" :key="module.code"
         @click="goModule(module)"
    >
      <base-icon class="my-bottom-bar__item-color">{{ module.icon }}</base-icon>
      <div>{{ module.title }}</div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "myBottomBar",
  data: () => ({
    list: [
      {icon: 'mdi-home-outline', title: "Главная", code: "main"},
      {icon: 'mdi-bell-outline', title: "Уведомления", code: "notifications"},
      {icon: 'mdi-chart-timeline-variant', title: "Сводка", code: "graphs"},
      {icon: 'mdi-help-circle-outline', title: "Гид", code: "guide"},
      {icon: 'mdi-account-circle-outline', title: "Аккаунт", code: "account"},
    ]
  }),
  computed: {
    // Код выбранного модуля
    selectedModuleCode() {
      return this.$route.name?.split("-")[0];
    }
  },
  methods: {
    goModule({ code }) {
      console.log(code);
      this.$router.push({ name: code });
    }
  }
}
</script>

<style lang="scss" scoped>
.my-bottom-bar {
  position: fixed;
  bottom: 0;
  height: 50px;
  padding: 0 $sz--hor-padding;
  width: calc(100% - #{2*$sz--hor-padding});
  border-top: 1px solid $color--light-gray;
  display: grid;
  grid-template-columns:  repeat(5, 1fr);

  &__item {
    padding-top: 4px;
    height: 100%;
    text-align: center;
    font-size: $fs--mini;

    & > * {color: $color--light-gray !important}
    &.selected > * {color: $color--blue !important}
  }
}
</style>
