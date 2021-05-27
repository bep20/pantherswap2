<template>
  <div class="lottery_wrapper">
    <div class="col1">
      <h4 class="heading">The PANTHER Lottery</h4>
      <p class="title" style="margin-top: 1rem">Buy tickets with PANTHER</p>
      <p class="title">Win if 2, 3 or 4 of your ticket numbers match!</p>
    </div>
    <div class="col2">
      <div class="progress_wrapper">
        <div class="inner_wrapper"></div>
      </div>
      <h2 class="time_details">
        <span>0h, 23m</span>
        Until ticket sale
      </h2>
      <p class="subTitle">0h, 21m Until lottery draw</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Lottery"
};
</script>

<style scoped lang="scss">
@import "../theme/scss/variables.scss";
.lottery_wrapper {
  background: linear-gradient(
    139.73deg,
    rgb(31, 96, 111) 0%,
    rgb(22, 72, 101) 100%
  );
  padding: 3.5rem 4rem;
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
.col1 {
  width: 50%;
}
.col2 {
  width: 50%;
}
.heading {
  color: $orange;
  font-size: 1.5rem;
}
.title {
  font-size: 1rem;
  font-weight: 600;
  color: $white;
}
.progress_wrapper {
  background-color: $darkGray;
  border-radius: 1rem;
  height: 1rem;
}
.inner_wrapper {
  background-color: $orange;
  width: 70%;
  border-radius: 1rem;
  height: 1rem;
}
.time_details {
  margin-top: 1rem;
  color: $white;
  text-align: center;
  & span {
    color: $orange;
  }
}
.subTitle {
  font-size: 1rem;
  color: $white;
  text-align: center;
}
</style>