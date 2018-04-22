<template>
    <div>
        <img :src="curs[currency]" alt="DUCATUR">
        <p v-if="label">{{ currency }}</p>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

import Currencies from '../CurrencyImages'

export default Vue.extend({
    data()
    {
        return {
            curs: Currencies
        }
    },
    props: ["currency", "label"]
})
</script>
<style scoped>
div {
    display: inline-block;
    width: 100px;
}
p {
    text-align: center;
    font-family: 'Nunito Sans', sans-serif;
}
img {
}

.logo-small {
    width: 80px;
}
.logo-small > img {
    width: 60px;
    padding-left: 10px;
}
.logo-small > p {
    font-size: 18px;
}
</style>
