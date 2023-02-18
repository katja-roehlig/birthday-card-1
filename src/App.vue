<script setup>
import HeadingComponent from "./components/HeadingComponent.vue";
import PresentComponent from "./components/PresentComponent.vue";
import OverlayComponent from "./components/OverlayComponent.vue";
import { ref } from "vue";

let overlay = ref(false);

function toggleOverlay() {
  overlay.value = !overlay.value;
}
</script>

<template>
  <div class="background">
    <HeadingComponent />
    <PresentComponent @changeOverlay="toggleOverlay()" />
    <OverlayComponent v-if="overlay" @changeOverlay="toggleOverlay()" />
  </div>
</template>

<style scoped>
.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
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
  background-image: linear-gradient(transparent 50%, hsla(253, 55%, 15%, 0.816)),
    url(./assets/daniel-olah-VUGAcY35Ubw-unsplash.jpg);
  background-size: 100%, cover;
  background-repeat: no-repeat;
  height: 100vh;
  padding: 6rem 3rem 5rem 3rem;
  position: relative;
}
</style>
