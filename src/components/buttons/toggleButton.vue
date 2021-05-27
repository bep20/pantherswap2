<template>
  <div class="toggler_wrapper">
    <div class="toggle_button_wrapper">
      <CustomButton
        text="Next draw"
        :variant="active==='Next draw' ? 'active': 'inactive'"
        :onClick="nextDrawClick"
      />
      <CustomButton
        text="Past draws"
        :variant="active==='Past draws' ? 'active': 'inactive'"
        :onClick="nextDrawClick"
      />
    </div>
  </div>
</template>

<script>
import CustomButton from "../buttons/custombutton.vue";

export default {
  name: "ToggleButton",
  components: {
    CustomButton
  },
  data() {
    return {
      active: "Next draw"
    };
  },
  methods: {
    nextDrawClick() {
      if (this.active === "Next draw") {
        this.active = "Past draws";
      } else {
        this.active = "Next draw";
      }
    }
  }
};
</script>

<style scoped lang="scss">
@import "../../theme/scss/variables.scss";
.toggler_wrapper {
}
.toggle_button_wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 2rem;
  border-radius: 2rem;
  max-width: 15.75rem;
  background-color: $darkGray;
  margin: auto;
  height: 3.25rem;
}
</style>