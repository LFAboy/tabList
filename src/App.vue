<script setup>
import { ref } from "vue";

const isBtnActive = ref(0);
</script>


<template>
  <div class="tab-container">
    <header class="header">
      <span
        class="tab-button"
        :class="{ active: isBtnActive == 0 }"
        @click="isBtnActive = 0"
        >热门球员</span
      >
      <span
        class="tab-button"
        :class="{ active: isBtnActive == 1 }"
        @click="isBtnActive = 1"
        >热门球队</span
      >
    </header>
    <main>
      <div v-show="isBtnActive == 0" class="tab-list palyer">
        <div class="tab-item">
          <div class="photo">
            <img src="/images/messi.png" alt="梅西" />
            <span class="rate">1</span>
          </div>
          <div class="description">
            <span>梅西</span>
            <div class="hot-bar">
              <div class="inner">532341热度</div>
            </div>
          </div>
        </div>
      </div>
      <div v-show="isBtnActive == 1" class="tab-list team">
        <div class="tab-item">
          <div class="photo">
            <img src="/images/messi.png" alt="梅西" />
            <span class="rate">1</span>
          </div>
          <div class="description">
            <span>法国</span>
            <div class="hot-bar">
              <div class="inner-bar">532341热度</div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
.tab-container {
  box-sizing: border-box;
  width: 800px;
  margin: 20px auto;
  padding: 30px;
  background-color: #2d53d3;
}

.header {
  display: flex;
  font-size: 24px;
  align-content: center;
  border-radius: 10px;
  overflow: hidden;
  /* 当子元素也有背景颜色时，上述设置的圆角就不会显示，这时需要我们溢出隐藏 */
  background-color: #fff;
}
.tab-button {
  flex: auto;
  padding: 10px 0;
  text-align: center;
  transition: background-color 0.2s ease-in-out;
  cursor: pointer;
}

.tab-button:not(.active):hover {
  color: #bb0334;
}
.tab-button.active {
  color: #fff;
  background-color: #bb0334;
}

.tab-list {
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  background-color: #2d53d3;
  padding: 20px;
}
.tab-item {
  display: flex;
  margin-bottom: 20px;
}
.photo {
  width: 150px;
  position: relative;
  border-radius: 20px;
  overflow: hidden;
  background-color: #fff;
}
.photo img {
  width: 100%;
  vertical-align: bottom;
}

.rate {
  display: flex;
  width: 40px;
  height: 40px;
  font-size: 20px;
  color: #fff;
  position: absolute;
  top: 0;
  left: 0;
  justify-content: center;
  align-items: center;
  border-bottom-right-radius: 20px;
  background-color: #F56601;
}

.description {
  display: flex;
  width: 100%;
  margin-left: 20px;
  color: #fff;
  font-size: 20px;
  flex-direction: column;
  justify-content: space-evenly;
  /* background-color: #fff; */
}
.hot-bar {
  background-color: #032567;
  border-radius: 20px;
  overflow: hidden;
}
.inner {
  padding: 8px;
  white-space: nowrap;
  text-indent: .5em;
  background-color: red;
  background-image: linear-gradient(90deg, #BB0334 50%, #43020E);
}
</style>