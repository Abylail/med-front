<template>
  <div class="main-page">
    <my-header title="Главная"/>

    <!-- Расписание -->
    <time-table/>

    <!-- Сообщение от доктора -->
    <doctor-message/>

  </div>
</template>

<script>
import MyHeader from "@/components/common/layout/myHeader.vue";
import TimeTable from "@/components/common/timeTable/timeTable.vue";
import DoctorMessage from "@/components/common/cards/doctorMessage.vue";

export default {
  name: "index",
  components: {DoctorMessage, TimeTable, MyHeader}
}
</script>

<style scoped>

</style>
