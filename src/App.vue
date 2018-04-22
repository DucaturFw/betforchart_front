<template>
  <div id="app">
    <app-header/>
    <div v-if="loading">Loading...</div>
    <bets-list v-if="!loading && !modeCreate"/>
    <create-bet v-if="!loading && modeCreate" :currency="create.currency" @create-bet="createBet"/>
    <app-footer/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AppHeader from './common/Header.vue'
import AppFooter from './common/Footer.vue'
import BetsList from './bets/List.vue'
import CreateBet from './create/Create.vue'

export default Vue.extend({
  data() {
    return {
      modeCreate: window.location.pathname == "/create",
      loading: false,
      create: {
        currency: "Bitcoin",
      }
    }
  },
  methods: {
    createBet(form: {cur: string, cond: string, price1: number, price2: number, date: number})
    {
      console.log(`create bet: ${JSON.stringify(form)}`)
    }
  },
  mounted: function ()
  {
    console.log()
    let _this = this
    setTimeout(() => {
      _this.loading = false
    }, 1000)
  },
  components: {
    AppHeader,
    AppFooter,
    BetsList,
    CreateBet,
  }
})
</script>