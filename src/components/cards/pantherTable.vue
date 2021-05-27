<template>
  <div class="card">
    <div class="card__header">
      <div class="card__avatar"></div>
      <div class="card__info__wrapper">
        <p>Total Pot</p>
        <h2>PANTHER</h2>
      </div>
    </div>
  </div>
</template>

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
}
</style>