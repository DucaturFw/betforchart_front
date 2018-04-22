<template>
  <div id="footer">
    <div class="footer-container">
      <div class="grid-container">
        <div class="subscribe">
            <input type="email" name="" id="" placeholder="Email">
            <button>Subscribe</button>
        </div>
        <logo class="logo"/>
        <div class="icons">
          <img v-for="icon in icons" :key="icon" :src="icon">
        </div>
        <div class="copyright">©2018 DUCATUR on hackathon</div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">

import Vue from 'vue'
import Logo from './Logo.vue'
export default Vue.extend({
  data()
  {
    return {
      icons: [
        "https://a.icons8.com/0jpnglvr/g1ftC9/twitter-(1)normal.png",
        "https://a.icons8.com/0jpnglvr/xjizae/facebook-(1)normal.png",
        "https://a.icons8.com/0jpnglvr/5cYzxg/telegramnormal.png",
        "https://a.icons8.com/0jpnglvr/X3DzhY/discordnormal.png",
      ],
    }
  },
  components: {
    Logo
  }
})

</script>

<style scoped>

span.link {
  margin: 40px;
}
span.link > a {
  /* color: white; */
  /* text-decoration: none; */
}

div#footer {
  width: 100%;
  font-family: 'Nunito Sans', sans-serif;
  /* background: darkcyan;
  color: white; */
  min-height: 320px;
  position: relative;
  background: url(https://a.icons8.com/0jpnglvr/B8dh8N/rectanglenormal.svg) 0px 0px / calc(100% + 200px) no-repeat;
}
div.footer-container {
  position: absolute;
  bottom: 0;
  width: 100%;
}
.grid-container {
  display: grid;
  width: 100%;
  grid-template-columns: 450px auto 300px;
  grid-template-rows: auto auto;
  bottom: 40px;
  position: absolute;
}

div.subscribe {
  margin-top: 10px;
  margin-left: 100px;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
}
div.subscribe > input {
  /* padding: 10px; */
  border: none;
  border-radius: 4px;
  width: 200px;
  height: 38px;
  font-size: 18px;
  padding-left: 10px;
}
div.subscribe > button {
  width: 109px;
  height: 41px;
  border: none;
  color: white;
  font-size: 18px;
  margin-left: 10px;
  background: url(https://a.icons8.com/0jpnglvr/FxTRjr/rectangle-2normal.png);
}

.logo {
  display: block;
  margin: auto;
  padding-right: 150px;
}

div.icons {
  float: right;
  margin-right: 40px;
}
div.icons > img {
  margin-right: 10px;
  margin-top: 10px;
}

div.copyright {
  display: block;
  margin: auto;
  text-align: center;

  grid-column-start: 2;
  padding-right: 150px; /* unfortunately neede by the grid */
  
  color: rgba(255,255,255,0.5);
  font-family: 'Nunito Sans', sans-serif;
  font-size: 18px;
}

</style>