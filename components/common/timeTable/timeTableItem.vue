<template>
  <div class="time-table-item" :class="[`time-table-item--status-${info.status}`]">
    <div class="time-table-item__tick"/>
    <div class="time-table-item__time">{{ info.time }}</div>
    <div class="time-table-item__content">{{ info.text }}</div>
    <div class="time-table-item__action"></div>
  </div>
</template>

<script>
export default {
  name: "timeTableItem",
  props: {
    info: {
      type: Object,
      default: () => ({time: "11:00", text: "Выпить лекарство", status: "completed"})
    }
  }
}
</script>

<style lang="scss" scoped>
@mixin line {
  display: block;
  content: "";
  position: absolute;
  bottom: calc(100% + 3px);
  left: 6px;
  height: 19px;
  width: 2px;
  border-left: 2px solid $color--light-gray;
}

.time-table-item {
  height: 20px;
  display: grid;
  grid-template-columns: 20px 40px 1fr 60px;
  align-items: center;
  grid-column-gap: 10px;
  position: relative;

  &__tick {
    height: 16px;
    width: 16px;
    background: $color--light-gray;
    border-radius: 16px;
  }

  &__time {
    font-weight: bold;
  }

  &__content {
    color: $color--gray;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  &--status-completed {
    &:not(:first-child) {
      margin-top: 25px;
      &::after {
        @include line;
      }
    }
  }

  &--status-active {
    color: $color--green;
    .time-table-item__tick {
      background: $color--green;
    }

    &:not(:first-child) {
      margin-top: 45px;
      &::after {
        @include line;
        height: 39px;
        left: 6px;
        border-left: 4px dashed $color--green;
      }
    }
  }
}
</style>
