<template>
  <div class="time-table">
    <div class="time-table__title">Расписание</div>

    <div class="time-table__content">
      <time-table-item :info="{time: '11:00', text: 'Выпить лекарство', status: 'completed'}"/>
      <time-table-item :info="{time: '11:30', text: 'Измерить давление', status: 'completed'}"/>
      <time-table-item :info="{time: '16:30', text: 'Измерить давление', status: 'completed'}"/>
      <time-table-item :info="{time: '18:30', text: 'Измерить давление', status: 'active'}"/>
    </div>

    <div class="time-table__action" v-if="haveAction">
      <base-button full-width>Измерить давление</base-button>
    </div>
  </div>
</template>

<script>
import TimeTableItem from "@/components/common/timeTable/timeTableItem.vue";

export default {
  name: "timeTable",
  components: {TimeTableItem},
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
    font-weight: bold;
  }

  &__content {
    margin: 20px 0;
  }

  &__item-wrapper {
    display: flex;
    flex-direction: row;
  }
}
</style>
