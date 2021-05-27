<template>
  <div class="card">
    <div class="header">
      <div class="avatar"></div>
      <div class="info_wrapper">
        <p>Total Pot</p>
        <h2>PANTHER</h2>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
@import "../../theme/scss/variables.scss";
.card {
  background-color: $darkBlue;
  background-color: rgb(18, 24, 39);
  border-radius: 2rem;
  box-shadow: rgb(25 19 38 / 10%) 0px 2px 12px -8px,
    rgb(25 19 38 / 5%) 0px 1px 1px;
  color: $white;
}
.info_wrapper {
  & p {
    font-size: 0.875rem;
    color: $orange;
  }
  & h2 {
    font-size: 1.5rem;
    font-weight: 600;
  }
}
</style>