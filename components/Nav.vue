<template>
  <nav>
    <ul>
      <li v-for="link in links" :key="link.name">
        <nuxt-link
          :to="link.path"
          :id="`link-${link.name}`"
          :aria-current="link.path === $nuxt.$route.path ? 'page' : false"
        >{{ link.name }}</nuxt-link>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  created() {
    this.$router.options.routes.forEach(route => {
      if (route.path !== '/') {
        this.links.push({
          name: route.name.replace('-', ' '),
          path: route.path
        })
      }
    })
  },
  data() {
    return {
      links: []
    }
  }
}
</script>

<style scoped>
nav {
  height: 100%;
  display: grid;
  align-items: center;
}
ul {
  list-style: none;
  display: flex;
  width: 100%;
}
li {
  display: inline-block;
  width: 100%;
  text-align: center;
  text-transform: uppercase;
  font-family: 'Playfair Display', serif;
  font-size: 1.4em;
}
a {
  position: relative;
  overflow: hidden;
  display: inline-block;
  padding: 0.6em 0.2em;
}
a:after {
  content: '';
  background: linear-gradient(
      to right,
      transparent 0%,
      transparent 45%,
      white 50%,
      transparent 55%,
      transparent 100%
    ),
    linear-gradient(
      115deg,
      #8c8c8c 1.3%,
      #999 15%,
      #868686 29.6%,
      #828282 29.6%,
      #7d7d7d 31.8%,
      #797979 31.8%,
      #6a6a6a 38.9%,
      white
    );
  background-position: 110% 0%, 0 0;
  background-size: 200% auto, auto;
  opacity: 0.3;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  position: absolute;
  transition: all 0.4s ease-in-out;
  transform: translateY(200%);
}
a:hover:after,
a:active:after,
a:focus:after,
a[aria-current]:after {
  z-index: -1;
  transform: translateY(0%);
}
@media screen and (max-width:600px) {
    li {
        font-size: 1em;
    }
    li:first-child {
        margin-left: -3em;
    }
    li:nth-child(2) {
        margin-left: -2em;
    }
    li:nth-child(3) {
        margin-right: -2em;
    }
    li:last-child {
        margin-right: -3em;
    }
    a {
        padding: 1.1em 0.2em;
    }
}
</style>
