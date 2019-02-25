<template>
  <header>
    <h1>Mary Miller Beauty</h1>
    <Nav/>
    <nuxt-link
      class="home-link"
      to="/"
      name="index"
      :aria-current="'/' === $nuxt.$route.path ? 'page' : false"
      aria-label="Home"
    >
      <Logo/>
      <svg aria-hidden class="text">
        <text x="25%" y="50%">Beauty</text>
      </svg>
    </nuxt-link>
  </header>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Nav from '~/components/Nav.vue'

export default {
  components: {
    Logo,
    Nav
  }
}
</script>

<style scoped>
h1 {
  opacity: 0;
  height: 0;
  width: 0;
  overflow: hidden;
}
header {
  position: fixed;
  height: 56px;
  width: 100vw;
  display: grid;
  grid-auto-columns: calc(50% - 50px) 100px calc(50% - 50px);
  align-items: center;
  padding: 0.5em;
  background: black;
  justify-items: center;
  z-index: 10;
}
header:before,
header:after {
  content: '';
  width: 100vw;
  height: 2px;
  position: fixed;
  left: 0;
  transform: translateY(3em);
}
header:before {
  mix-blend-mode: soft-light;
  background-image: linear-gradient(
    to left,
    white,
    black,
    white,
    black,
    white,
    black,
    white
  );
  z-index: -2;
}
header:after {
  color: #858585;
  animation: shine 16s ease-in-out infinite;
  background-position: 110% 0%, 0 0;
  background-size: 200% auto, auto;
  background-image: linear-gradient(
      to right,
      transparent 0%,
      transparent 45%,
      white 50%,
      transparent 55%,
      transparent 100%
    ),
    linear-gradient(
      270deg,
      #8c8c8c 1.3%,
      #999 15%,
      #868686 29.6%,
      #828282 29.6%,
      #7d7d7d 31.8%,
      #797979 31.8%,
      #6a6a6a 38.9%,
      #d3d3d3
    );
  z-index: -3;
}

@keyframes shine {
  0% {
    background-position: 110% 0%, 0 0;
  }
  90% {
    background-position: 110% 0%, 0 0;
  }
  100% {
    background-position: -10% 0%, 0 0;
  }
}
header > * {
  grid-area: none;
}
.text {
  transform: translateY(50%) translateX(-4%);
  filter: drop-shadow(0 0 1px black);
  position: absolute;
  left: 0;
  right: 0;
  margin: auto;
  height: 100px;
}
text {
  fill: var(--colorRed);
  font-family: 'Lipstick', cursive;
  font-size: 4em;
  position: absolute;
  transform: rotate(6deg);
  margin: auto;
}
nav {
  position: absolute;
  width: 90%;
}
.home-link {
  display: inline-block;
  height: 100%;
  width: 100%;
}
</style>
