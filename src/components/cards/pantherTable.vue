<template>
  <div class="card">
    <div class="card__header">
      <div class="card__avatar"></div>
      <div class="card__info__wrapper">
        <p>Total Pot</p>
        <h2>PANTHER</h2>
      </div>
    </div>
    <div class="card__body">
      <div class="card__body__item__header">
        <p>No. Matched</p>
        <p>Prize Pot</p>
      </div>
      <div class="card__body__item__body" v-for="item in table" :key="item.id">
        <p>{{item.id}}</p>
        <p>{{item.pot}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PantherTable",
  data() {
    return {
      table: [
        { id: 4, pot: 2150 },
        { id: 3, pot: 760 },
        { id: 2, pot: 200 },
        { id: 1, pot: 100 }
      ]
    };
  }
};
</script>

<style scoped lang="scss">
@import "../../theme/scss/variables.scss";
.card {
  &__avatar {
    width: 4rem;
    height: 4rem;
    background-color: $darkGray;
    border-radius: 50%;
    margin-right: 1rem;
  }
  &__header {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding-bottom: 1rem;
    border-bottom: 1px solid $darkGray;
  }
  &__info__wrapper {
    & p {
      font-size: 0.875rem;
      color: $orange;
    }
    & h2 {
      font-size: 1.5rem;
      font-weight: 600;
    }
  }
  &__body {
    &__item__header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      color: $orange;
    }
    &__item__body {
      display: flex;
      align-items: center;
      justify-content: space-between;
      color: $white;
    }
  }
}
</style>