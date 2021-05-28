<template>
  <div class="sidebar">
    <div class="sidebar__item" v-for="item in sidebar" :key="item.name">
      <img :src="item.img" :alt="item.name" />
      <p></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Sidebar",
  data() {
    return {
      sidebar: [{ img: "/images/lottery.svg", name: "Lottery" }]
    };
  }
};
</script>

<style scoped lang="scss">
.sidebar {
  &__item {
    display: flex;
    align-items: center;
  }
}
</style>