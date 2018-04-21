<template>
  <div class="main-list">
      <h1>Контракты на спор</h1>
      <ul>
          <li>bitcoin</li>
          <li>litecoin</li>
          <li>ripple</li>
          <li>ethereum</li>
          <li>...</li>
      </ul>
      <div class="sort">
          <p>Упорядочить</p>
          <select name="" id=""></select>
      </div>
      <div id="betsList">
          <bet class="bet-entry" v-for="(bet, key, index) in bets" :key="index" :bet="bet" :complete="key % 2"></bet>
      </div>
  </div>
</template>

<script lang="ts">

import Vue from 'vue'
import Bet from './Bet.vue'

export default Vue.extend({
    data()
    {
        return {
            bets: [
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
                { cur: "Bitcoin", price: 10000, date: 1274128974 },
            ]
        }
    },
    components: {
        Bet,
    }
})

</script>

<style scoped>

.bet-entry {
    left: 150px;
    width: 400px;
}
div.main-list {
    width: 80%;
    left: auto;
    right: auto;
}

</style>