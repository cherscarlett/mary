<template>
  <section>
    <h2>Location</h2>
    <div class="head-container">
      <div class="gallery">
        <div>
          <img
            src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/31891079_178984782757357_6409436496763289600_o.jpg?_nc_cat=101&_nc_ht=scontent-msp1-1.xx&oh=78d47dbf4e399a2316162aa7cfe73ca0&oe=5D21DCE2"
          >
        </div>
        <div>
          <img
            src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/31520305_178984826090686_403049476337434624_o.jpg?_nc_cat=101&_nc_ht=scontent-msp1-1.xx&oh=3924c5ae4bf1eef36422c8b6fe019793&oe=5CE62CC8"
          >
        </div>
        <div>
          <img
            src="https://scontent-msp1-1.xx.fbcdn.net/v/t1.0-9/31948885_178984859424016_221398468822827008_o.jpg?_nc_cat=107&_nc_ht=scontent-msp1-1.xx&oh=749558c7b3728d547fd70b4afbe5bbdf&oe=5CE9A15B"
          >
        </div>
      </div>
      <div id="map"></div>
      <div id="infowindow-content">
        <strong>Mary Miller Beauty</strong>
        <br>
        <span id="place-name" class="title"></span>
        <br>
        <span id="place-address"></span>
        <br>
        <br>
        <a href="https://salonlofts.com/mary_emiller/schedule">Book Online</a> &nbsp;|&nbsp;
        <a id="directions">Get Directions</a>
      </div>
    </div>
    <div class="address">
      <div class="business">
        <h3>Mary Miller Beauty</h3>
        <img src="http://www.besalon.me/images/426_logo_4237f81ffb4b52d1ae07fbd1304af6475.jpg">
      </div>
      <address>
        <a
          href="https://www.google.com/maps/place/Salon+Lofts/@38.6031355,-90.4408091,17z/data=!3m1!5s0x87d8cd9baf60186b:0xe8c76fea25966240!4m8!1m2!3m1!2sSalon+Lofts!3m4!1s0x0:0xdd1f41dadbae56d3!8m2!3d38.6038623!4d-90.4383246"
        >12139 Manchester Rd
          <br>Des Peres, MO 63131
        </a>
        <br>
        <a href="tel:314-956-9224">314.956.9224</a>
      </address>
    </div>
  </section>
</template>

<script>
export default {
  transition: 'slide',
  mounted() {
    const salon = { lat: 38.6031355, lng: -90.4408091 }
    const map = new google.maps.Map(document.getElementById('map'), {
      zoom: 12,
      name: 'Mary Miller Beauty',
      center: salon
    })
    const service = new google.maps.places.PlacesService(map)
    service.getDetails(
      {
        placeId: 'ChIJhXEVnpvN2IcR01au29pBH90'
      },
      function(result, status) {
        const marker = new google.maps.Marker({
          map: map,
          place: {
            placeId: 'ChIJhXEVnpvN2IcR01au29pBH90',
            location: result.geometry.location
          }
        })
        console.log(result)
        const infowindow = new google.maps.InfoWindow()
        const infowindowContent = document.getElementById('infowindow-content')
        infowindow.setContent(infowindowContent)
        infowindowContent.children['place-name'].textContent = result.name
        infowindowContent.children['place-address'].textContent =
          result.formatted_address
        infowindowContent.children['directions'].href = result.url
        infowindow.open(map, marker)
        marker.addListener('click', function() {
          infowindow.open(map, marker)
        })
      }
    )
  }
}
</script>

<style scoped>
#infowindow-content {
  color: black;
}
#infowindow-content a {
  text-decoration: underline;
}
h2 {
  opacity: 0;
  height: 0;
  width: 0;
  overflow: hidden;
}
#map {
  height: 100%;
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
}
#map > div {
  mix-blend-mode: hard-light;
}
.head-container {
  display: grid;
  grid-template-columns: 50% 50%;
  grid-template-rows: 50vh;
  overflow: hidden;
}
.gallery {
  display: flex;
  justify-content: center;
}
.gallery > div {
  width: calc(100% / 3);
  display: flex;
  justify-content: center;
  overflow: hidden;
}
img {
  height: 50vh;
  filter: grayscale(100%) contrast(120%) brightness(120%) opacity(90%);
  transition: all 0.4s ease-in-out;
}
img:hover {
  filter: grayscale(0%) contrast(100%) brightness(100%) opacity(100%);
}
address {
  font-style: normal;
  padding-left: 2em;
}
a {
  color: black;
  display: inline-block;
  padding: 0 0 1em 0;
}
.address {
  display: grid;
  grid-template-columns: 50% 50%;
  color: var(--colorRed);
  padding: 2em 2em 0 2em;
  font-size: 2em;
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
      #797979 31.8%,
      #6a6a6a 38.9%,
      white
    );
  background-position: 110% 0%, 0 0;
  background-size: 200% auto, auto;
  height: calc(50vh - 57px);
}
.business {
  position: relative;
  text-align: right;
  padding: 0 2em 0 0;
}
.business:after {
  content: 'j';
  font-family: lipstick, cursive;
  font-size: 12em;
  transform: scale(-1) rotate(-25deg) translateX(-15%) translateY(5%);
  position: absolute;
  top: 0;
  right: 0;
}
h3 {
  font-size: 1.5em;
  margin: 0;
  color: black;
}
.business img {
  mix-blend-mode: multiply;
  position: absolute;
  width: 250px;
  height: auto;
  transform: translateY(-25%);
  right: 10%;
}
section {
  overflow: hidden;
}

@media screen and (max-width: 900px) {
.head-container {
  grid-template-columns: 100%;
}
#map {
    height: 50vh;
}
.address {
    grid-template-columns: 100%;
    height: auto;   
    padding:.5em .5em 0 .5em;
}
h3 {
    font-size: 1em;
}
address {
    padding: 3em 0 .5em 0;
}
}
</style>
