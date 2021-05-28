<template>
  <div class="header">
    <WalletConnect v-if="showModal" :onClose="handleModal" />
    <i class="fa fa-bars menu_icon" aria-hidden="true"></i>
    <CustomButton text="connect" :onClick="handleModal" />
  </div>
</template>

<script>
import CustomButton from "./buttons/custombutton.vue";
import WalletConnect from "./cards/walletConnect.vue";

export default {
  name: "Header",
  components: {
    CustomButton,
    WalletConnect
  },
  data() {
    return {
      showModal: false
    };
  },
  methods: {
    handleModal() {
      console.log("running")
      this.showModal = !this.showModal;
    }
  }
};
</script>

<style lang="scss">
@import "../theme/scss/variables.scss";

body {
  font-family: "Mitr", sans-serif;
}

.header {
  background-color: rgb(18, 24, 39);
  height: 4rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 1rem;
}
.menu_icon {
  font-size: 1.5rem;
  color: $white;
  cursor: pointer;
}
.contact {
  background-color: $orange;
  color: $white;
  padding: 0.5rem;
  font-family: "Mitr", sans-serif;
}
</style>
