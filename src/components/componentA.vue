<template>
    <p>資料綁定(單向綁定)</p>
    {{ data }}

    <p>資料綁定(雙向綁定)</p>
    <input type="text" v-model="text" />
    <p>{{ text }}</p>
</template>

<script setup>
import { ref } from 'vue';

// 資料驅動畫面
const data = 'Hello Vue'
const text = ref("雙向綁定!")

</script>

<style scoped></style>
