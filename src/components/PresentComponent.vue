<script setup>
const emit = defineEmits(["changeOverlay", "update:name"]);

function btnClick() {
  emit("changeOverlay");
}
</script>
<script>
export default {
  props: ["name"],
  emits: ["update:name"],
};
</script>

<!-- html ---------------------------------------------------------------------------------->
<template>
  <div class="present__container">
    <div class="present__ribbon left"></div>
    <div class="present__ribbon right"></div>

    <div class="present">
      <div class="present__tape-vertical"></div>
      <div class="present__tape-horizontal">
        <div class="btn__container">
          <label for="birthday-name" class="visually-hidden"
            >Name eingeben</label
          >
          <input
            type="text"
            class="name__input"
            id="birthday-name"
            placeholder="Name eingeben"
            required
            :value="name"
            @input="$emit('update:name', $event.target.value)"
          />
          <button class="name__btn" @click.prevent="btnClick()">
            auspacken
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<!-- style ------------------------------------------------------------------------------->
<style scoped>
.present__container {
  position: absolute;
  z-index: 0;
  top: 58vh;
  animation: move-present-vertical 1s cubic-bezier(0.575, 0.885, 0.32, 1.2) 1.2s
      1 both,
    move-present-horizontal 0.1s linear 2.2s 3;
}
.present {
  width: 28rem;
  height: 21rem;
  border-radius: 0.5rem;
  box-shadow: 0px 0px 15px var(--shadow-color),
    inset 0px 0px 20px var(--shadow-color);
  background-image: radial-gradient(
    circle,
    var(--present-color) 25%,
    var(--present-color-dark) 25%
  );
  background-size: 20% 20%;
  position: relative;
  z-index: 2;
}
.present__tape-vertical {
  width: 5rem;
  height: 100%;
  background-image: linear-gradient(
    var(--ribbon-color) 0%,
    rgba(249, 184, 55, 0.951),
    var(--ribbon-color) 100%
  );
  box-shadow: 0px 0px 3px 0px rgba(105, 42, 53, 0.198);
}

.present__tape-horizontal {
  width: 100%;
  height: 5rem;
  background-image: linear-gradient(
    90deg,
    var(--ribbon-color) 0%,
    var(--ribbon-color-accent),
    var(--ribbon-color) 100%
  );
  position: absolute;
  top: 40%;
  z-index: 1;
}
.present__ribbon {
  height: 4rem;
  border-radius: 0.5rem;
  position: absolute;
  z-index: 1;
}

.left {
  background-image: linear-gradient(
    90deg,
    var(--ribbon-color-accent),
    var(--ribbon-color) 70%
  );
  width: 12rem;
  height: 3.5rem;
  transform: rotate(30deg);
  transform-origin: right bottom;
  top: -8%;
  right: 48%;
  box-shadow: -2px -5px 5px var(--shadow-color);
}
.right {
  background-image: linear-gradient(
    90deg,
    var(--ribbon-color) 30%,
    rgb(249, 185, 55)
  );
  width: 15rem;
  transform: rotate(-47deg);
  transform-origin: left bottom;
  top: -5%;
  right: -4%;
  box-shadow: 0px 0px 3px 0px rgba(105, 42, 53, 0.198),
    5px 5px 8px var(--shadow-color);
  animation: rotate-ribbon-right 1.5s linear 3.5s infinite;
}

.name__input {
  background-color: rgb(236, 201, 136);
  border: 1px solid white;
  height: 3rem;
  border-radius: 1rem;
  padding-left: 0.8rem;
  box-shadow: 0px 0px 7px var(--ribbon-color);
  color: var(--present-color-dark);
  width: 50%;
}
.btn__container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  animation: show-button 2s linear 3.1s both;
}

.visually-hidden {
  clip: rect(0 0 0 0);
  clip-path: inset(50%);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}

.name__btn {
  height: 2.8rem;
  border-radius: 1rem;
  font-size: 1.2rem;
  border: none;
  padding: 0.1rem 1rem 0rem 1rem;
  color: rgb(241, 226, 199);
  background-color: var(--present-color-dark);
  box-shadow: 0px 0px 3px white;
  text-transform: uppercase;
}
.name__btn:hover {
  transform: scale(1.05);
  background-color: var(--present-color);
}
/* Keyframes ************************************************************************************* */
@keyframes move-present-vertical {
  0% {
    opacity: 0.3;
    transform: translateY(-100vh);
  }
  100% {
    opacity: 1;
    transform: translateY(0vh);
  }
}
@keyframes move-present-horizontal {
  0%,
  100% {
    transform: translateX(0px);
  }
  25% {
    transform: translateX(2px);
  }
  75% {
    transform: translateX(-2px);
  }
}
@keyframes show-button {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes rotate-ribbon-right {
  0%,
  100% {
    transform: rotate(-47deg);
  }
  25% {
    transform: rotate(-45deg);
  }
  75% {
    transform: rotate(-49deg);
  }
}
@keyframes scale-button {
  0%,
  100% {
    transform: scale(0.95);
  }
  50% {
    transform: scale(1);
  }
}
/* media queries ********************************************************** */
@media (min-width: 768px) {
  .present {
    width: 34rem;
    height: 25rem;
  }
  .present__container {
    top: 63vh;
  }
  .left {
    right: 50%;
  }
  .right {
    right: 4%;
  }
}
</style>
