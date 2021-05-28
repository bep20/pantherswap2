<template>
  <div class="sidebar">
    <div class="sidebar__item" v-for="item in sidebar" :key="item.name">
      <img :src="item.img" :alt="item.name" />
      <p>{{item.name}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sidebar",
  props: {
    full: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      sidebar: [{ img: "/images/lottery.svg", name: "Lottery" }]
    };
  }
};
</script>

<style scoped lang="scss">
@import "../theme/scss/variables.scss";
.sidebar {
  background-color: $darkBlue;
  padding: 1rem;
  &__item {
    display: flex;
    align-items: center;
    color: $white;
    & img {
      margin-right: 1rem;
    }
  }
}
</style>