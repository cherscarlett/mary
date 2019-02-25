<template>
  <section>
    <h2>Features</h2>
    <ul>
      <li>
        <nuxt-link to="/location" name="location">
          <img
            src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/31891079_178984782757357_6409436496763289600_o.jpg?_nc_cat=101&_nc_ht=scontent-msp1-1.xx&oh=78d47dbf4e399a2316162aa7cfe73ca0&oe=5D21DCE2"
          >
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/gallery" name="gallery">
          <video autoplay loop muted>
            <source type="video/mp4" src="//i.imgur.com/fxaUeWg.mp4">
          </video>
        </nuxt-link>
      </li>
      <li>
        <nuxt-link to="/about" name="about">
          <img
            src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/50620587_302844853704682_5595861672473395200_n.jpg?_nc_cat=103&_nc_ht=scontent-msp1-1.xx&oh=bba8da4821e7f9abaa293e6de647cdf0&oe=5D268434"
          >
        </nuxt-link>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  transition: 'slide'
}
</script>

<style scoped>
h2 {
  opacity: 0;
  height: 0;
  width: 0;
  overflow: hidden;
}
ul {
  display: flex;
  width: 100%;
  list-style: none;
  height: calc(100vh - 50px);
  flex-wrap: nowrap;
  overflow: hidden;
}

li {
  transition: all 0.4s ease-in-out;
  width: calc(100% / 3);
  overflow: hidden;
  display: flex;
  justify-content: center;
  filter: grayscale(100%) contrast(120%) brightness(120%) opacity(90%);
  flex-shrink: 1;
}
li > img,
li > iframe {
  min-height: 100%;
  width: auto;
  flex: none;
}

a:before {
  content: '';
  position: absolute;
  z-index: 1;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #fff;
  opacity: 0.3;
  transform-origin: center center;
  transform: skew(-45deg) scaleY(1) translate(0, 0);
  transition: all 0.6s cubic-bezier(0.17, 1, 0.83, 1);
}

li a:hover:before {
  transform: skew(-45deg) scale(3) translate(0, 0);
  opacity: 0;
}
li:hover {
  width: 50%;
  filter: grayscale(10%) contrast(100%) brightness(100%) opacity(100%);
}
</style>
