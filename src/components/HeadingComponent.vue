<template>
  <div class="heading__container heading__happy">
    <h1 class="heading">Happy</h1>
  </div>
  <div class="heading__container heading__birthday">
    <h1 class="heading">Birthday</h1>
  </div>
</template>

<!-- Styles************************************************************ -->
<style scoped>
.heading {
  text-align: center;
  font-size: 7rem;
  padding-block: 0.7rem;
}
.heading__container {
  background-image: linear-gradient(var(--ribbon-color), yellow);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  filter: drop-shadow(2px 2px 15px black);
}
.heading__happy {
  animation: move-happy 0.5s cubic-bezier(0.25, 0.46, 0.45, 1.94) 0.3s 1 both;
}
.heading__birthday {
  animation: move-birthday 0.3s cubic-bezier(0.25, 0.46, 0.45, 1.94) 0.3s 1 both;
}
/* keyframes ********************************************************** */
@keyframes move-happy {
  0% {
    transform: translateX(-100vw);
  }
  100% {
    transform: translateX(0vw);
  }
}
@keyframes move-birthday {
  0% {
    transform: translateX(100vw);
  }
  100% {
    transform: translateX(0vw);
  }
}
/* media queries ********************************************************* */
@media (min-width: 768px) {
  .heading {
    font-size: 8rem;
    margin-top: 2.5rem;
  }
}
</style>
