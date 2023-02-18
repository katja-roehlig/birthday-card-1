<script setup>
import HeadingComponent from "./components/HeadingComponent.vue";
import PresentComponent from "./components/PresentComponent.vue";
</script>

<template>
  <div class="background">
    <HeadingComponent />
    <PresentComponent />
  </div>
</template>

<style scoped>
.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  /* background-image: linear-gradient(
      rgba(0, 0, 0, 0.867) 20%,
      rgba(0, 0, 0, 0.026),
      rgba(0, 0, 0, 0.967) 80%
    ),
    repeating-radial-gradient(
      rgba(0, 0, 0, 0.574),
      rgba(0, 0, 0, 0.132) 1px,
      white 7px,
      white 10px
    ); 
  background-size: cover, 25% 20%;
  background-repeat: no-repeat, repeat;*/
  background-image: url(./assets/daniel-olah-VUGAcY35Ubw-unsplash.jpg);
  background-size: cover;
  background-repeat: no-repeat;
  height: 100vh;
  padding: 5rem 3rem;
}
</style>
