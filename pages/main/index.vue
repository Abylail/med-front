<template>
  <div class="main-page">
    <my-header title="Главная"/>

    <time-table/>
  </div>
</template>

<script>
import MyHeader from "@/components/common/layout/myHeader.vue";
import TimeTable from "@/components/common/timeTable/timeTable.vue";

export default {
  name: "index",
  components: {TimeTable, MyHeader}
}
</script>

<style scoped>

</style>
