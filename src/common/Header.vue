<template>
  <div id="header">
      <logo/>
      <div class="menu-main">
        <span class="link" v-for="menuLink in menuLinks" :key="menuLink.name"><a :href="menuLink.href">{{ menuLink.name }}</a></span>
        <span>Whitepaper</span>
        <span id="menu">☰</span>
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
  background: darkcyan;
  width: 1258px;
  height: 53px;
  color: #272a31;
  /* font-family: Montserrat; */
  font-size: 18px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 500;
  text-align: left;
}

div.logo {
  /* float: left; */
}
div.menu-main {
  /* float: right; */
}

</style>