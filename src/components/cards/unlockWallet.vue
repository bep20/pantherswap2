<template>
  <div class="card">
    <p class="unlock_wallet_text">Click Here to Participate</p>
    <div style="text-align:center">
      <div class="inputbox">
        <input v-model="first_number" type="number" @change="handleSearch" /> &nbsp;
        <input v-model="second_number" type="number" @change="handleSearch" />&nbsp;
        <input v-model="third_number" type="number" @change="handleSearch" />&nbsp;
        <input v-model="fourth_number" type="number" @change="handleSearch" />&nbsp;
      </div>
      <CustomButton v-on:click="participate()" text="Participate" />
    </div>
  </div>

  <div id="card" class="card">
    <p class="unlock_wallet_text">Approve Token to Participate on Lottery</p>
    <div style="text-align:center">
      <CustomButton v-on:click="approve()" text="Approve Token" />
    </div>
  </div>
</template>
<script>
import CustomButton from "../buttons/custombutton.vue";
import BEP20 from "../../abi/BEP20";
import Lottery from "../../abi/Lottery";
import Web3 from "web3";
export default {
  name: "UnlockWallet",
  components: {
    CustomButton,
  },
  data() {
    return {
      numInput: 0,
      admin_token: 0,
      first_number: 0,
      second_number: 0,
      third_number: 0,
      fourth_number: 0,
      maxNumber: "",
      minimumNumber: 0,
      claim_reward: 0,
      testnet: `https://kovan.infura.io/v3/e0737333518f412892d21b1762e8fe47`,
      web3: new Web3(
        Web3.givenProvider || new Web3.providers.HttpProvider(this.testnet)
      ),
      lottery: "0x81D7928657d092bc72CF4cd9b4cF274AE86952F2",
      bep: "0x93971Ff38e86d9075bA34440387C7590d3a3F5A6",
    };
  },
  methods: {
    claimReward: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;
      this.web3.eth.getAccounts().then(async (addresses) => {
        methods.claimReward(this.claim_reward).send({
          from: addresses[0],
          gas: 2100000,
          gasPrice: "210000",
        });
      });
    },

    minimum: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;
      this.web3.eth.getAccounts().then(async (addresses) => {
        methods.setMinPrice(this.minimumNumber).send({
          from: addresses[0],
          gas: 2100000,
          gasPrice: "210000",
        });
      });
    },

    sendAdmin: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;

      this.web3.eth.getAccounts().then(async (addresses) => {
        methods.adminWithdraw(this.admin_token).send({
          from: addresses[0],
          gas: 2100000,
          gasPrice: "210000",
        });
      });
    },

    setMaxNumber: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;
      this.web3.eth.getAccounts().then(async (addresses) => {
        methods.setMaxNumber(this.maxNumber).send({
          from: addresses[0],
          gas: 2100000,
          gasPrice: "210000",
        });
      });
    },

    draw: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;
      this.web3.eth.getAccounts().then(async (addresses) => {
        methods.drawing(this.numInput).send({
          from: addresses[0],
          gas: 2100000,
          gasPrice: "210000",
        });
      });
    },

    participate: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;
      this.web3.eth.getAccounts().then(async (addresses) => {
        methods
          .buy(10000, [
            this.first_number,
            this.second_number,
            this.third_number,
            this.fourth_number,
          ])
          .send({
            from: addresses[0],
            gas: 2100000,
            gasPrice: "210000",
          });
      });
    },

    enterDrawingPhase: async function () {
      const methods = await new this.web3.eth.Contract(
        Lottery.abi,
        this.lottery
      ).methods;
      this.web3.eth.getAccounts().then(async (addresses) => {
        methods.enterDrawingPhase().send({
          from: addresses[0],
          gas: 2100000,
          gasPrice: "210000",
        });
      });
    },

    approve: async function () {
      const methods = await new this.web3.eth.Contract(BEP20.abi, this.bep20)
        .methods;
      this.web3.eth.getAccounts().then(async (data) => {
        await methods
          .approve(this.lottery, 1000000) // hydrolottery hashcode
          .send({
            from: data[0],
            gas: 210000,
            gasPrice: "21000",
          });
      });
    },
  },
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

.inputbox {
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

.card {
  margin-bottom: 2rem;
}
</style>