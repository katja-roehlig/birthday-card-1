<script setup>
const emit = defineEmits(["changeOverlay"]);
function divClick() {
  emit("changeOverlay");
}
</script>
<template>
  <div class="overlay__container" @click="divClick">
    <h2 class="subheading">Huhuu</h2>
    <p>
      wie schön, dass du heute Geburtstag hast.<br />
      Ich wünsche dir alles alles Liebe und Gute -ganz viel Glück 🍀, Erfolg,
      Gesundheit und Liebe ❤️.
    </p>
    <p>Lass es dir gut gehen!</p>
    <p>Liebe Grüße, Katja</p>
  </div>
</template>

<style scoped>
.overlay__container {
  width: 100%;
  height: 100vh;
  background-color: rgba(255, 255, 255, 0.577);
  position: absolute;
  top: 0%;
}
</style>
