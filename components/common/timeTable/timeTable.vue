<template>
  <div class="time-table">
    <div class="time-table__title">Расписание</div>

    <div class="time-table__content">

    </div>

    <div class="time-table__action" v-if="haveAction">
      <base-button full-width>Измерить давление</base-button>
    </div>
  </div>
</template>

<script>
export default {
  name: "timeTable",
  computed: {

    // Есть ли какое то действие
    haveAction() {
      return true;
    }
  }
}
</script>

<style lang="scss" scoped>
.time-table {
  margin: 30px 0;
  padding: 0 $sz--hor-padding;

  &__title {
    font-size: $fs--title;
  }
}
</style>
