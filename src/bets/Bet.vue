<template>
  <div class="bet-entry">
    <span class="text-main">{{ bet.cur }} по ${{ bet.price }} к {{ bet.date }}</span>
    <input v-if="complete" class="btn" type="button" value="Участвовать">
  </div>
</template>

<script lang="ts">

import Vue from 'vue'
export default Vue.extend({
  data()
  {
    return {
      menuLinks: [
      ],
    }
  },
  props: ["bet", "complete"],
  components: {
  }
})

</script>

<style scoped>

span.text-main {
    width: 80%;
}
input.btn {
    width: 20%;
}

</style>