<template>
  <div class="header">
    <ul class="header-button-left">
      <li>Cancel</li>
    </ul>
    <ul class="header-button-right">
      <li>Next</li>
    </ul>
    <img src="./assets/logo.png" class="logo" alt="로고입니다.">
  </div>

  <ContainerBox :dataList = "dataList"></ContainerBox>

  <div class="footer">
    <ul class="footer-button-plus">
      <input type="file" id="file" class="inputfile">
      <label for="file" class="input-plus">+</label>
    </ul>
  </div>
</template>

<script>

import blogData from './data';
import ContainerBox from './components/Container.vue';

export default {
  name: 'App',
  data(){
    return{
      dataList : blogData,
    }
  },
  components: {
    ContainerBox: ContainerBox,

  }
}
</script>

<style>
@import 'style.css';

#app {
box-sizing: border-box;
font-family: "consolas";
margin-top: 60px;
width: 100%;
max-width: 460px;
margin: auto;
position: relative;
border-right: 1px solid #eee;
border-left: 1px solid #eee;
}
</style>
