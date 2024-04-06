<template>

    <button @click="changeView(1)">顯示單向綁定</button>
    <button @click="changeView(2)">顯示雙向綁定</button> <!--// 你知道其實@click就等同於v-on:click嗎-->
    <button @click="changeView(1000)">沒畫面</button>


    <div class="container-1" v-if="view === 1">

        <p>資料綁定(單向綁定)</p>
        {{ data }}
    </div>
    <div class="container-2" v-if="view === 2">
        <p>資料綁定(雙向綁定)</p>
        <input type="text" v-model="text" />
        <p>{{ text }}</p>
    </div>



    <div v-if="view !== 2 && view !== 1">
        沒畫面
    </div>
</template>

<script setup>
import { ref } from 'vue';

// 資料驅動畫面
const data = 'Hello Vue'
const text = ref("雙向綁定!")
const view = ref(1)

const changeView = (index) => {
    view.value = index
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
