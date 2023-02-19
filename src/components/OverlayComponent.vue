<script setup>
import { ref, defineProps } from "vue";
const emit = defineEmits(["changeOverlay"]);
function divClick() {
  emit("changeOverlay");
}
let isPlaying = ref(false);
function handleMusic() {
  isPlaying.value = true;
}
const props = defineProps({ name: String });
</script>

<!-- html ---------------------------------------------------------------------------------------->
<template>
  <div class="overlay__container">
    <p class="fotograf">Photo by Maria</p>
    <h2 class="subheading">Huhuu {{ props.name }},</h2>
    <div class="text__container">
      <p class="text text__main">
        wie schön, dass Du heute Geburtstag hast!<br />
        Ich wünsche Dir alles, alles Liebe und Gute: <br />
        ganz viel Glück 🍀, Erfolg, Gesundheit und Liebe ❤️ für Dein neues
        Lebensjahr.
      </p>
      <p class="text text__last">Lass es Dir gut gehen!</p>
    </div>
    <p class="text text__sender">Katja</p>
    <button class="btn btn__music" @click="handleMusic()">
      🎶 Ein Lied für Dich
    </button>
    <audio src="/happy-birthday-crowd.mp3 " type="audio/mp3" autoplay>
      Music!
    </audio>

    <audio
      controls
      src="/happy-birthday-guitar.mp3"
      type="audio/mp3"
      autoplay
      v-if="isPlaying"
    ></audio>

    <button @click="divClick" class="btn btn__back">↩︎</button>
  </div>
</template>

<style scoped>
.fotograf {
  color: #aa096a78;
  font-size: 1.1rem;
  position: absolute;
  bottom: 2%;
  right: 6%;
}
audio {
  filter: opacity(0.6);
  position: absolute;
  bottom: 2%;
  left: 6%;
}
.overlay__container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  opacity: 0.98;
  width: 100%;
  height: 100vh;
  background-image: url(../assets/maria-cake-mittel.webp);
  background-size: 130% 140%;
  background-repeat: no-repeat;
  background-position: 10% 30%;
  position: absolute;
  top: 0%;
  padding: 4.5rem 0rem;
  text-align: center;
}
.subheading {
  margin-bottom: 1.5rem;
  color: var(--overlay-color-dark);
}
.text__container {
  width: 100%;
  text-align: center;
}
.text__main {
  line-height: 3rem;
  width: 38ch;
}
.text__last {
  margin-top: 2rem;
}
.text__sender {
  margin: 0px;
}
.btn {
  padding: 1rem 1.5rem;
  border-style: none;
  border-radius: 0.8rem;
  background-color: var(--overlay-color);
  font-weight: bold;
  color: var(--overlay-color-dark);
  margin: 0px;
  box-shadow: inset 0px 0px 10px 1px var(--overlay-color-dark),
    0px 0px 2px var(--shadow-color);
}
.btn:hover {
  background-color: var(--overlay-color-dark);
  color: white;
}

.btn__back {
  position: absolute;
  bottom: 10%;
  right: 6%;
  font-size: 3rem;
  padding: 0.5rem 1.5rem 0rem 1.5rem;
}
.btn__music {
  font-size: 1.6rem;
  position: absolute;
  bottom: 10%;
  left: 6%;
}

/* media queries ******************************************************************/
@media (min-width: 768px) {
  .overlay__container {
    width: 60vw;
  }
  .text {
    font-size: 1.8rem;
    line-height: 3.2rem;
  }
  .subheading {
    font-size: 3.3rem;
    margin-top: 2rem;
    margin-bottom: 2rem;
  }
  .btn__music {
    left: 10%;
  }
  .btn__back {
    right: 10%;
  }
}
</style>
