<template>
  <div class="main-create">
    <div id="curSelector">
        <h3>Спор на прогноз курса</h3>
        <h1>Выберите монету</h1>
        <div class="cur-select" v-for="(cur, _, index) in currencies" :key="index" @click="selectCur(cur)">
            <span v-if="selectedCur == cur.name">selected!</span>
            {{ cur.name }}
        </div>
        <button>Другая монета</button>
    </div>

    <div id="createForm">
        <h1>Ваш прогноз на {{ selectedCur }}</h1>
        <div>logo</div>
        <div>datepicker</div>
        <span>Условие</span>
        <select name="condition" id="cond" v-model="form.cond"></select>
        <span>Прогноз стоимости</span>
        <input type="text" name="price1" id="price1" v-model="form.price1">
        <span>Прогноз стоимости 2</span>
        <input type="text" name="price2" id="price2" v-model="form.price2">
        <button id="btnCreate" @click="create">Создать спор</button>
    </div>
  </div>
</template>

<script lang="ts">

import Vue from 'vue'

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
    }
})

</script>

<style scoped>


</style>