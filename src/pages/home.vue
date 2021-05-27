<template>
  <div>
    <Header />
    <Lottery />
    <div class="cards_wrapper">
      <ToggleButton />
      <div class="grid__wrapper">
        <div class="grid_col_1">
          <PantherTable />
        </div>
        <div class="grid_col_2">
          <UnlockWallet />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "../components/header.vue";
import Lottery from "../components/lottery.vue";
import ToggleButton from "../components/buttons/toggleButton.vue";
import PantherTable from "../components/cards/pantherTable.vue";
import UnlockWallet from "../components/cards/unlockWallet.vue";

export default {
  name: "Home",
  components: {
    Header,
    Lottery,
    ToggleButton,
    PantherTable,
    UnlockWallet,
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
  justify-content: space-between;
  flex-wrap: wrap;
  margin-top: 2rem;
}
.grid_col_1,
.grid_col_2 {
  width: calc(50% - 1rem);
}
</style>