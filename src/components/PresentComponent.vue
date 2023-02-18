<template>
  <div class="present__container">
    <div class="present__ribbon left"></div>
    <div class="present__ribbon right"></div>

    <div class="present">
      <div class="present__tape-horizontal">
        <input type="text" class="name__input" placeholder="Name eingeben" />
        <button class="name__btn">Click"</button>
      </div>
      <div class="present__tape-vertical"></div>
    </div>
  </div>
</template>
<style scoped>
.present__container {
  position: absolute;
  z-index: 0;
  top: 60%;
}
.present {
  width: 28rem;
  height: 21rem;
  border-radius: 0.5rem;
  box-shadow: 0px 0px 15px var(--shadow-color),
    inset 0px 0px 20px var(--shadow-color);
  /* background-image: repeating-linear-gradient(
    30deg,
    var(--present-color),
    var(--present-color) 20px,
    var(--present-color-dark) 20px,
    var(--present-color-dark) 25px
  ); */
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
  height: 21.2rem;
  background-image: linear-gradient(
    var(--ribbon-color) 0%,
    rgba(249, 184, 55, 0.951),
    var(--ribbon-color) 100%
  );
  position: relative;
  top: -25%;
  box-shadow: 0px 0px 3px 0px rgba(105, 42, 53, 0.198);
}

.present__tape-horizontal {
  width: 28.2rem;
  height: 5rem;
  --background-color: var(--ribbon-color);
  background-image: linear-gradient(
    90deg,
    var(--ribbon-color) 0%,
    rgb(249, 185, 55),
    var(--ribbon-color) 100%
  );
  position: relative;
  top: 40%;
  z-index: 1;
}
.present__ribbon {
  height: 4rem;
  --background-color: var(--ribbon-color);
  border-radius: 0.5rem;
  position: absolute;
  z-index: 1;
}

.left {
  background-image: linear-gradient(
    90deg,
    rgb(249, 185, 55),
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
}

.name__input {
  background-color: rgb(236, 201, 136);
  border: none;
  height: 3rem;
  border-radius: 0.8rem;
}
</style>
