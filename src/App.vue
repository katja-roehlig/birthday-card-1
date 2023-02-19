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
<script>
export default {
  components: { PresentComponent },
  data() {
    return {
      name: "",
    };
  },
};
</script>

<template>
  <div class="background">
    <p class="fotograf">Photo by Daniel Olah</p>
    <HeadingComponent />
    <PresentComponent @changeOverlay="toggleOverlay()" v-model:name="name" />
    <OverlayComponent
      v-if="overlay"
      @changeOverlay="toggleOverlay()"
      :name="name"
    />
  </div>
</template>

<style scoped>
.background {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.5rem;
  background-image: linear-gradient(transparent 50%, hsla(253, 55%, 15%, 0.816)),
    url(./assets/daniel-olah-feuerwerk-mittel.webp);
  background-size: 100%, cover;
  background-repeat: no-repeat;
  height: 100vh;
  padding: 6rem 3rem 5rem 3rem;
  position: relative;
}
.fotograf {
  color: rgba(240, 51, 82, 0.523);
  font-size: 1.1rem;
  position: absolute;
  bottom: 2%;
  right: 4%;
}

/* media queries ***************************************************************************/
@media (min-width: 768px) {
  .background {
    width: 60vw;
    padding-bottom: 3rem;
  }
}
</style>
