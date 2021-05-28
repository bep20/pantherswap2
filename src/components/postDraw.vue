<template>
  <div class="grid__wrapper">
    <WalletConnect v-if="showWallet" :onClose="handleWallet" />
    <div class="grid_col_1">
      <div class="input__container">
        <p class="lotnumer">Select Lottery Number</p>
        <div class="lottery__input">
          <input type="text" @change="handleSearch" />
          <CustomButton text="Search" />
        </div>
      </div>

      <div class="card">
        <div class="id_container">
          <p class="id">Round #1</p>
          <p class="date">
            May 01, 2:00 UTC
            Round #1
          </p>
        </div>
        <div class="number__prize__container">
          <div class="avatar"></div>
          <div class="info">
            <p>Winning numbers</p>
            <h2>1, 12, 11, 4</h2>
          </div>
        </div>
        <div class="number__prize__container">
          <div class="avatar"></div>
          <div class="info">
            <p>Total prizes</p>
            <h2>14,048 PANTHER</h2>
          </div>
        </div>
        <div class="card_table_wrapper">
          <div class="table_header_xser">
            <p>No. Matched</p>
            <p>Winners</p>
            <p>Prize Pot</p>
          </div>
          <div class="table_body_xser" v-for="item in table" :key="item.id">
            <p>{{item.id}}</p>
            <p>{{item.winner}}</p>
            <p>{{item.pot}}</p>
          </div>
        </div>
        <div class="flex">
          <CustomButton text="Unlock Wallet" style="margin:auto" :onClick="handleWallet" />
        </div>
      </div>
    </div>
    <div class="grid_col_2"></div>
  </div>
</template>

<script>
import CustomButton from "./buttons/custombutton.vue";
import WalletConnect from "./cards/walletConnect.vue";

export default {
  name: "PostDraw",
  components: {
    CustomButton,
    WalletConnect
  },
  data() {
    return {
      table: [
        { id: 4, winner: 0, pot: "7,024" },
        { id: 3, winner: 0, pot: "7,024" },
        { id: 2, winner: 0, pot: "7,024" },
        { id: 1, winner: 0, pot: "7,024" }
      ],
      showWallet: false
    };
  },
  methods: {
    handleSearch(e) {
      console.log(e.target.value);
    },
    handleWallet() {
      this.showWallet = !this.showWallet;
    }
  }
};
</script>

<style scoped lang="scss">
@import "../theme/scss/variables.scss";
.lotnumer {
  color: $white;
}
.lottery__input {
  border-radius: 1rem;
  padding: 0.5rem;
  background-color: $darkGray;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 2rem;

  & input {
    width: 100%;
    background-color: transparent;
    border: none;
    height: 2rem;
    font-size: 1rem;
    color: $white;
    font-family: "Mitr", sans-serif;
    &:focus {
      outline: none;
    }
  }
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
.id_container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 1rem;
  .id {
    font-weight: 600;
    color: $white;
  }
  .date {
    color: $white;
  }
}
.number__prize__container {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
  .avatar {
    width: 4rem;
    height: 4rem;
    background-color: $blue;
    border-radius: 50%;
    margin-right: 1rem;
  }
  p {
    color: $orange;
  }
}
.table_header_xser {
  display: flex;
  align-items: center;
  justify-content: space-between;
  color: $orange;
  border-top: 1px solid $darkGray;
  padding-top: 1rem;
}
.table_body_xser {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: 500;
  color: $white;
}
.flex {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-top: 1rem;
  button {
    padding-top: 0.6rem;
    padding-bottom: 0.6rem;
  }
}
</style>