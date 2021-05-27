<template>
  <div class="card">
    <p class="unlock_wallet_text">Unlock wallet to access lottery</p>
    <div style="text-align:center">
      <CustomButton text="Unlock Wallet" />
    </div>
  </div>
</template>
<script>
import CustomButton from "../buttons/custombutton.vue";
export default {
  name: "UnlockWallet",
  components: {
    CustomButton
  }
};
</script>

<style scoped lang="scss">
@import "../../theme/scss/variables.scss";

.unlock_wallet_text {
  font-weight: 600;
  font-size: 1.25rem;
  text-align: center;
  margin-bottom: 1rem;
}
</style>