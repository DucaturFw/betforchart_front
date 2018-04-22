<template>
  <div id="app">
    <app-header/>
    <div v-if="loading">Loading...</div>
    <bets-list v-if="!loading && !modeCreate" @make-bet="listBetClick"/>
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
		createBet(form: {cur: "Ethereum" | "Bitcoin" | "Litecoin" | "Ripple", cond: string, price1: number, price2: number, date: number})
		{
			const SHORT = {
				Ethereum: "ETH",
				Bitcoin: "BTC",
				Litecoin: "LTC",
				Ripple: "XRP",
			}

			console.log(`create bet: ${JSON.stringify(form)}`)

			fetch('/create_bet', {
				method: 'POST',
				body: JSON.stringify({
					bet_info: {
						for_amount: form.price1,
						value: form.price2,
						currency: SHORT[form.cur],
						datetime: form.date,
					},
					user_info: { email: "test_user@mail.ru" }
				}),
				headers: new Headers({
					'Content-Type': 'application/json'
				})
			}).then(() => { window.location.href = '/' })
			/*
			{
			bet_info: {for_amount: 1000, value: 50, currency: "ETH"},
			user_info: {email: "unique id"}
			}
			*/
		},
		listBetClick(bet: {})
		{
			console.log(`bet clicked: ${JSON.stringify(bet)}`)
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

<style>
@import url("https://fonts.googleapis.com/css?family=Nunito+Sans:400,700|Montserrat:400,700");
html {
  width: 100%;
  background: url(https://a.icons8.com/yuoUhPeZ/ZM8xcN/page-1normal.png) repeat-y -400px;
  background-size: calc(100% + 800px);
  background-color: #a2c4eb;
}
html, body {
  margin: 0;
}
</style>
