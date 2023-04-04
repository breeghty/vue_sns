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
  <button @click="clCnt++; more()">더보기</button>

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
import axios from 'axios';

export default {
  name: 'App',
  data(){
    return{
      dataList : blogData,
      clCnt : 0,
    }
  },
  methods :{
    more(){

      //axios.post('url', {name : 'kim"}).then(성공시).catch(실패시)
      // post는 url로 원하는 데이터를 보낼 수 있는 함수.
      if(this.clCnt == 1){
        axios.get('https://codingapple1.github.io/vue/more0.json')
        .then((result)=>{
          //요청성공시 실행할 코드
          //console.log(result.data);
          // dataList 배열에 result.data를 추가
          this.dataList.push(result.data);
        })
      }
      else if(this.clCnt == 2){
        axios.get('https://codingapple1.github.io/vue/more1.json')
        .then((result) =>{
          this.dataList.push(result.data);
        })
      }
      
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
