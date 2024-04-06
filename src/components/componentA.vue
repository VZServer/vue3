<template>

    <button v-on:click="changeView">顯示單向綁定</button>
    <button>顯示雙向綁定</button>


    <div class="container-1" v-if="view === 1">

        <p>資料綁定(單向綁定)</p>
        {{ data }}
    </div>
    <div class="container-2" v-if="view === 2">
        <p>資料綁定(雙向綁定)</p>
        <input type="text" v-model="text" />
        <p>{{ text }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue';

// 資料驅動畫面
const data = 'Hello Vue'
const text = ref("雙向綁定!")
const view = ref(1)

const changeView = () => {
    view.value = 2
}

</script>

<style scoped>
.container-1 {
    border: 2px red solid;
}

.container-2 {
    border: 2px blue solid;
}
</style>
