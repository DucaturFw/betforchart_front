<template>
  <div class="main-list">
      <h1>Betting Contracts</h1>
      <a href="/create" class="invis"><button class="more">Create new bet</button></a>
      <cur-logo class="logo-small" v-for="cur in currencies" :key="cur" :currency="cur" :label="true"></cur-logo>
      <div class="sort">
          <p>Sort by:</p>
          <select name="" id="" disabled><option value="">Date added</option></select>
      </div>
      <div id="betsList">
          <bet class="bet-entry" v-for="(bet, key, index) in bets" :key="index" :bet="bet" :complete="key % 2" @make-bet="makeBet"></bet>
      </div>
  </div>
</template>

<script lang="ts">

import Vue from 'vue'
import Bet from './Bet.vue'
import CurLogo from '../partials/CurrencyLogo.vue'

export default Vue.extend({
    data()
    {
        return {
            currencies: ["Bitcoin", "Litecoin", "Ripple", "Ethereum"]
        }
    },
    props: ["bets"],
    methods: {
        makeBet(bet: any)
        {
            this.$emit('make-bet', bet)
        }
    },
    components: {
        Bet,
        CurLogo,
    }
})

</script>

<style scoped>

.bet-entry {
    margin-bottom: 20px;
}
div.main-list {
  width: 770px;
  /* height: 1054px; */
  font-family: 'Nunito Sans', sans-serif;
  font-size: 17px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 400;
  text-align: left;
  margin: auto;
}
h1 {
  /* width: 750px; */
  height: 52px;
  /* color: #fff; */
  color: #211F51;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  font-size: 48px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 700;
  text-align: center;
}

div.sort {
    /* display: inline-block; */
    float: right;
    /* bottom: 0; */
    margin-top: 15px;
}
div.sort > p {
    font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
    font-size: 17px;
    font-weight: 700;
    /* text-align: right; */
}
div.sort > select {
    padding: 8px;
    border-radius: 4px;
    width: 250px;
}


button.more {
  /* width: 20%; */
  border: none;
  border-radius: 25px;
  width: 248px;
  height: 55px;
  background: #ff1052;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  color: white;
  font-size: 18px;
  /* font-weight: 700; */
  margin: auto;
  margin-bottom: 40px;
  display: block;
  cursor: pointer;
}
a.invis {
    text-decoration: none;
}

</style>