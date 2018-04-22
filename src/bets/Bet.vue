<template>
  <div class="bet-entry">
    <span class="text-main">{{ bet.cur }} at ${{ bet.price }} on {{ bet.date }}</span>
    <input v-if="!complete" class="btn" type="button" value="Bet">
    <img class="check" v-if="complete" src="https://a.icons8.com/bbpXpmkk/0iOHYM/btnnormal.png" alt="V">
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
  /* width: 20%; */
  border: none;
  border-radius: 25px;
  width: 149px;
  height: 36px;
  background: #ff1052;
  color: white;
  font-size: 18px;
  font-weight: 700;
  margin-top: -7px;
  float: right;
  cursor: pointer;
}

img.check {
  margin-top: -7px;
  float: right;
}

div.bet-entry {
  border-radius: 8px;
  /* width: 770px; */
  /* height: 68px; */
  background: #ffffff;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  color: #211f51;
  box-shadow: 0px 1px 3px rgba(32,32,38,0.12);
  padding: 20px;
  padding-left: 30px;
  padding-right: 30px;
}
span.text-main {
  /* top: 25px; */
  /* height: 25px; */
  color: #272a31;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  font-size: 18px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 500;
  text-align: left;
}

</style>