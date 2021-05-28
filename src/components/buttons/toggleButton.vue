<template>
  <div class="toggler_wrapper">
    <div class="toggle_button_wrapper">
      <CustomButton
        text="Next draw"
        :variant="active==='Next draw' ? 'active': 'inactive'"
        :onClick="onToggle"
      />
      <CustomButton
        text="Past draws"
        :variant="active==='Past draws' ? 'active': 'inactive'"
        :onClick="onToggle"
      />
    </div>
  </div>
</template>

<script>
import CustomButton from "../buttons/custombutton.vue";

export default {
  name: "ToggleButton",
  props: {
    onToggle: {
      type: Function
    },
    active: {
      type: String
    }
  },
  components: {
    CustomButton
  }
};
</script>

<style scoped lang="scss">
@import "../../theme/scss/variables.scss";
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