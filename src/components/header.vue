<template>
  <div class="header">
    <i class="fa fa-bars menu_icon" aria-hidden="true"></i>
    <CustomButton text="connect" />
  </div>
</template>

<script>
import CustomButton from "./buttons/custombutton.vue";

export default {
  name: "Header",
  components: {
    CustomButton
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
}
.contact {
  background-color: $orange;
  color: $white;
  padding: 0.5rem;
  font-family: "Mitr", sans-serif;
}
</style>
