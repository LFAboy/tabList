<script setup>
import { ref, reactive, provide } from "vue";
import TabHeader from '@/views/TabHeader/index.vue';
import TabMain from './views/TabMain/index.vue'

const isBtnActive = ref(0);
provide('isBtnActive', isBtnActive)

</script>

<template>
  <div class="tab-container">
    <TabHeader></TabHeader>
    <TabMain></TabMain>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
:root {
  --whiteBgc: #fff;
  --brownBgc: #bb0334;
  --blueBgc: #2d53d3;
}
.tab-container {
  box-sizing: border-box;
  width: 800px;
  margin: 20px auto;
  padding: 30px;
  background-color: var(--blueBgc);
}
</style>