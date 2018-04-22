<template>
  <div class="header-container">
  <div id="header">
      <logo class="logo"/>
      <div class="menu-main">
        <span class="link" v-for="menuLink in menuLinks" :key="menuLink.name"><a :href="menuLink.href">{{ menuLink.name }}</a></span>
        <button class="small-white-button">Whitepaper</button>
        <img class="burger" src="https://a.icons8.com/WiimnclY/gHp6pV/menu-iconnormal.png" alt="">
        <!-- <span id="menu">☰</span> -->
      </div>
      <!-- <div class="background"></div> -->
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
      menuLinks: [
        { name: "About", href: "/about" },
        { name: "Team", href: "/team" },
        { name: "Timeline", href: "/timeline" },
        { name: "FAQ", href: "/faq" },
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
  /* font-family: "Nunito Sans"; */
}
span.link > a {
  color: white;
  text-decoration: none;
}

/* div#header {
  background: darkcyan;
  color: white;
} */
div#header {
  width: 1258px;
  height: 53px;
  color: #272a31;
  /* font-family: Montserrat; */
  font-size: 18px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 500;
  text-align: left;
  margin: auto;
}

div.header-container {
  width: 100%;
  height: 150px;
  background: url(https://u.imageresize.org/808e0c8e-7320-4d53-adb4-73ff7f72c0b3.png) 0px -8px / calc(100% + 50px),
    url(https://a.icons8.com/WiimnclY/fxrxJO/rectanglenormal.svg) -10px -10px / calc(100% + 50px) no-repeat;
}

.logo {
  float: left;
  margin-top: 21px;
  margin-left: 40px;
}
div.menu-main {
  float: right;
  margin-right: 50px;
  margin-top: 31px;
  /* color: #211f51; */
}
div.menu-main > span {
  height: 20px;
  color: #ffffff;
  font-family: 'Nunito Sans', sans-serif;
  font-size: 15px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 400;
  text-align: left;
}
span#menu {
  /* color: #fff; */
  color: rgba(0, 0, 0, 0);
  width: 16px;
  background: url(https://a.icons8.com/WiimnclY/gHp6pV/menu-iconnormal.png);
}
img.burger {
  margin-left: 20px;
}
button.small-white-button {
  border: none;
  border-radius: 8px;
  width: 132px;
  height: 40px;
  color: #211f51;
  background: white;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  /* font-size: 48px; */
  font-style: normal;
  font-stretch: normal;
  font-weight: 700;
  text-align: center;
}

</style>