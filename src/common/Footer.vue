<template>
  <div id="footer">
      <div id="subscribe">
          <input type="email" name="" id="">
          <input type="button" value="">
      </div>
      <logo/>
      <ul>
          <li>twitter</li>
          <li>facebook</li>
          <li>telegram</li>
          <li>shit</li>
      </ul>
      <div id="copyright"></div>
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
}
span.link > a {
  /* color: white; */
  /* text-decoration: none; */
}

div#header {
  /* background: darkcyan;
  color: white; */
}

div.logo {
  /* float: left; */
}
div.menu-main {
  /* float: right; */
}

</style>