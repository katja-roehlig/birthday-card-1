<template>
  <div class="heading__container">
    <h1 class="heading heading__happy">Happy</h1>
  </div>
  <div class="heading__container">
    <h1 class="heading heading__birthday">Birthday</h1>
  </div>
</template>

<style scoped>
.heading {
  text-align: center;
  font-size: 6.5rem;
  padding-block: 0.5rem;
}
.heading__container {
  background-image: linear-gradient(var(--ribbon-color), yellow);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  filter: drop-shadow(2px 2px 5px black);
}
</style>
