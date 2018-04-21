<template>
  <div class="main-create">
    <div id="curSelector">
        <h3>Спор на прогноз курса</h3>
        <h1>Выберите монету</h1>
        <div class="cur-select" v-for="(cur, _, index) in currencies" :key="index">{{ cur.name }}</div>
        <button>Другая монета</button>
    </div>

    <div id="createForm">
        <h1>Ваш прогноз на {{ currency }}</h1>
        <div>logo</div>
        <div>datepicker</div>
        <span>Условие</span>
        <select name="condition" id="cond"></select>
        <span>Прогноз стоимости</span>
        <input type="text" name="price1" id="price1">
        <span>Прогноз стоимости 2</span>
        <input type="text" name="price2" id="price2">
        <button id="btnCreate">Создать спор</button>
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
            ]
        }
    },
    props: ["currency"],
    components: {
    }
})

</script>

<style scoped>


</style>