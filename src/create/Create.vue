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
        <button class="more">More currencies</button>
    </div>

    <div id="createForm">
        <h1 style="color: black; margin-top: 100px;">Your prediction for {{ selectedCur }}</h1>
        <div class="form-logo">
            <cur-logo :currency="selectedCur" :label="false"></cur-logo>
        </div>
        <div class="form-left">datepicker</div>
        <div class="form-right">
            <p>Condition</p>
            <select class="form-input" name="condition" id="cond" v-model="form.cond">
                <option value="">Price is between two values:</option>
            </select>
            <p>Price prediction 1</p>
            <input class="form-input" type="text" name="price1" id="price1" v-model="form.price1">
            <p>Price prediction 2</p>
            <input class="form-input" type="text" name="price2" id="price2" v-model="form.price2">
        </div>
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
                { name: "Bitcoin" },
                { name: "Litecoin" },
                { name: "Ripple" },
                { name: "Ethereum" },
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

button.more {
  /* width: 20%; */
  border: none;
  border-radius: 25px;
  width: 248px;
  height: 55px;
  background: #fff;
  font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
  color: black;
  font-size: 18px;
  /* font-weight: 700; */
  margin: auto;
  display: block;
  cursor: pointer;
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

div#createForm {
    width: 900px;
    margin: auto;
    font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
    font-size: 18px;
    /* height: 400px; */
}
div.form-logo {
    width: 100px;
    margin: auto;
}
div.form-left {
    width: 450px;
    height: 350px;
    float: left;
}
div.form-right {
    width: 450px;
    height: 350px;
    float: right;
}

.form-input {
    padding: 10px;
    border-radius: 4px;
    width: 400px;
    font-family: Montserrat, "Open Sans", Helvetica, Arial, sans-serif;
    font-size: 18px;
}
select.form-input {
    width: 425px;
}

div#createForm::after {
    clear: both;
    /* margin-bottom: 100px; */
    /* display: table; */
}
div.main-create {
    margin-bottom: 100px;
}
button#btnCreate {
    /* clear: both; */
    display: block;
    margin: auto;
}

</style>