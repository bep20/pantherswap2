<template>
  <div>
    <Header :onMenuClick="handleSidebar" />
    <div class="content__wrapper">
      <div :class="sidebarClass">
        <Sidebar :full="fullSidebar" />
      </div>
      <div :class="mainContentClass">
        <Lottery />
        <div class="cards_wrapper">
          <ToggleButton :onToggle="handleToggler" :active="activeSection" />
          <NextDraw v-if="activeSection==='Next draw'" />
          <PostDraw v-if="activeSection==='Past draws'" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "../components/header.vue";
import Sidebar from "../components/sidebar.vue";
import Lottery from "../components/lottery.vue";
import ToggleButton from "../components/buttons/toggleButton.vue";
import NextDraw from "../components/nextDraw.vue";
import PostDraw from "../components/postDraw.vue";

export default {
  name: "Home",
  components: {
    Header,
    Lottery,
    ToggleButton,
    Sidebar,
    NextDraw,
    PostDraw
  },
  data() {
    return {
      fullSidebar: true,
      sidebarClass: "full_sidebar",
      mainContentClass: "full_content",
      activeSection: "Next draw"
    };
  },
  methods: {
    handleSidebar() {
      console.log("hello");
      this.fullSidebar = !this.fullSidebar;
      if (this.sidebarClass === "full_sidebar") {
        this.sidebarClass = "half__sidebar";
      } else {
        this.sidebarClass = "full_sidebar";
      }

      if (this.mainContentClass === "full_content") {
        this.mainContentClass = "half__content";
      } else {
        this.mainContentClass = "full_content";
      }
    },
    handleToggler() {
      if (this.activeSection === "Next draw") {
        this.activeSection = "Past draws";
      } else {
        this.activeSection = "Next draw";
      }
    }
  }
};
</script>

<style scoped lang="scss">
@import "../theme/scss/variables.scss";
.cards_wrapper {
  background-color: $blue;
  padding: 2rem;
}
.content__wrapper {
  display: flex;
  height: calc(100vh - 4rem);
  overflow-y: hidden;
}

.full_sidebar {
  width: 15rem;
  align-self: stretch;
  background-color: $darkBlue;
  transition: all 0.4s;
}
.half__sidebar {
  width: 3.5rem;
  align-self: stretch;
  background-color: $darkBlue;
  transition: all 0.4s;
}
.full_content {
  width: calc(100% - 15rem);
  transition: all 0.4s;
  overflow-y: auto;
}
.half__content {
  width: calc(100% - 3.5rem);
  transition: all 0.4s;
  overflow-y: auto;
}
</style>