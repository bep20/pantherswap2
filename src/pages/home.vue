<template>
  <div>
    <Header />
    <Lottery />
    <div class="cards_wrapper">
      <ToggleButton />
      <div class="grid__wrapper">
        <div class="grid_col_1"></div>
        <div class="grid_col_2"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "../components/header.vue";
import Lottery from "../components/lottery.vue";
import ToggleButton from "../components/buttons/toggleButton.vue";

export default {
  name: "Home",
  components: {
    Header,
    Lottery,
    ToggleButton
  }
};
</script>

<style scoped lang="scss">
@import "../theme/scss/variables.scss";
.cards_wrapper {
  background-color: $blue;
  padding: 2rem;
}
.grid__wrapper {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
.grid_col_1,
.grid_col_2 {
  width: 50%;
}
</style>