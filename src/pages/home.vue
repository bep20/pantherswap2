<template>
  <Header />
  <Lottery />
</template>

<script>
import Header from "../components/header.vue";
import Lottery from "../components/lottery.vue";

export default {
  name: "Home",
  components: {
    Header,
    Lottery
  }
};
</script>
