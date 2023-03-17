<template>
  <div class="doctor-message card-shadow">
    <div class="doctor-message__avatar"/>
    <div class="doctor-message__content">
      <div class="doctor-message__head">
        <div class="doctor-message__name">{{ info.doctorName }}</div>
        <div class="doctor-message__time">{{ preparedDate }}</div>
      </div>
      <div class="doctor-message__text">{{ info.text }}</div>
      <div class="doctor-message__actions">
        <a class="doctor-message__action">Ответить</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "doctorMessage",
  data: () => ({
    info: {
      doctorName: "Фамилия и имя",
      date: "",
      text: "Вы молодец, надо продолжать в том же темпе"
    }
  }),
  computed: {
    // Обработанная дата
    preparedDate() {
      return "Вчера"
    }
  },
}
</script>

<style lang="scss" scoped>
.doctor-message {
  display: grid;
  grid-template-columns: 100px 1fr;
  grid-column-gap: 10px;
  margin: 20px $sz--hor-padding;
  padding: 10px;
  border-radius: 10px;

  &__avatar {
    height: 100px;
    width: 100px;
    background: $color--light-gray;
    border-radius: 10px;
  }

  &__head {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 10px 0;
    border-bottom: 1px solid $color--light-gray;
  }

  &__name {
    font-weight: bold;
  }

  &__time {
    font-size: $fs--mini;
    color: $color--gray;
  }

  &__text {
    padding-top: 5px;
    color: $color--gray;
  }

  &__actions {
    text-align: right;
  }

  &__action {
    color: $color--blue;
    font-weight: bold;
    font-size: $fs--mini;
  }

}
</style>
