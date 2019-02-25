<template>
  <div>
    <Header/>
    <nuxt/>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'

export default {
  components: {
    Header
  }
}
</script>

<style>
:root {
  --colorRed: #901230;
}
html {
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  background: black;
  color: white;
  font-family: 'Petrona', serif;
}

#__nuxt {
  min-width: 320px;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}
a {
  color: white;
  text-decoration: none;
}
section {
  padding-top: 57px;
}
ul {
  padding: 0;
}
.slide-enter-active,
.slide-leave-active {
  transition: all 600ms ease-out;
}
.slide-enter {
  transform: translateX(-100vw);
}
.slide-leave,
.slide-leave-active {
  transform: translateX(100vw);
}
</style>
