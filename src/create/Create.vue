<template>
  <div class="main-create">
    <div id="curSelector">
        <h3>Bet on price prediction</h3>
        <h1>Select currency</h1>
        <div class="curs-container">
            <div class="cur-select" :class="{ selected: selectedCur == cur.name }" v-for="(cur, _, index) in currencies" :key="index" @click="selectCur(cur)">
                <!-- <span v-if="selectedCur == cur.name">selected!</span> -->
                <cur-logo class="cur-logo" :currency="cur.name" :label="true"></cur-logo>
            </div>
        </div>
        <button>More currencies</button>
    </div>

    <div id="createForm">
        <h1>Your prediction for {{ selectedCur }}</h1>
        <div>logo</div>
        <div>datepicker</div>
        <span>Condition</span>
        <select name="condition" id="cond" v-model="form.cond"></select>
        <span>Price prediction 1</span>
        <input type="text" name="price1" id="price1" v-model="form.price1">
        <span>Price prediction 2</span>
        <input type="text" name="price2" id="price2" v-model="form.price2">
        <button id="btnCreate" @click="create">Place bet</button>
    </div>
  </div>
</template>

<script lang="ts">

import Vue from 'vue'
import CurLogo from '../partials/CurrencyLogo.vue'

export default Vue.extend({
    data()
    {
        return {
            currencies: [
                { name: "Bitcoin", img: "" },
                { name: "Litecoin", img: "" },
                { name: "Ripple", img: "" },
                { name: "Ethereum", img: "" },
            ],
            selectedCur: this.currency,
            form: {
                cond: "",
                price1: 0,
                price2: 0,
                date: 0,
            }
        }
    },
    methods: {
        create()
        {
            this.$emit('create-bet', { cur: this.selectedCur, ...this.form })
        },
        selectCur(cur: { name: string, img: string })
        {
            // console.log(`selected: ${cur.name}`)
            this.selectedCur = cur.name
        }
    },
    props: ["currency"],
    components: {
        CurLogo,
    }
})

</script>

<style scoped>

div.curs-container {
    width: 1240px;
    margin: auto;
}

h1 {
  /* width: 750px; */
  height: 52px;
  /* color: #fff; */
  color: #fff;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  font-size: 48px;
  font-style: normal;
  font-stretch: normal;
  font-weight: 700;
  text-align: center;
}
h3 {
    color: #ff1053;
    font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
    font-size: 24px;
    font-style: normal;
    font-stretch: normal;
    font-weight: 400;
    text-align: center;
}

div.cur-select {
    display: inline-block;
    background: rgba(32,32,38,0.08);
    padding: 40px 85px;
    padding-bottom: 20px;
    border-radius: 10px;
    margin: 20px;
    cursor: pointer;
}
div.cur-select.selected {
    background: white;
}
div.cur-select > .cur-logo {
    margin: auto;
}

</style>