<template>

  <div class="black-bg" v-if="모달창열림==true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="모달창열림=false">닫기</button>
    </div>
  </div>



  <div class="menu">
    <a v-for="작명 in menus" :key="작명">{{작명}}</a>
  </div>

  <!-- <div v-for="(a,i) in 3" :key="i">
    <h4>{{products[i]}}</h4>
    <p>50만원</p>
  </div>
  <div v-for="oneRoom in products" :key="oneRoom">
    <h4 :style="fnt">{{oneRoom}}</h4>
    <p>{{price1}} 만원</p>
  </div> -->

<!-- <div>
  <img src="./assets/room0.jpg" alt="" class="rom-img">
  <h4 @click="모달창열림=true">{{products[0]}}</h4>
  <p>50만원</p>
  <button @click="increase(0)">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
</div>
<div>
  <img src="./assets/room1.jpg" alt="" class="rom-img">
  <h4>{{products[1]}}</h4>
  <p>50만원</p>
  <button @click="increase(1)">허위매물신고</button>
  <span>신고수 : {{신고수[1]}}</span>
</div>
<div>
  <img src="./assets/room2.jpg" alt="" class="rom-img">
  <h4>{{products[2]}}</h4>
  <p>50만원</p>
  <button @click="increase(2)">허위매물신고</button>
  <span>신고수 : {{신고수[2]}}</span>
</div> -->

<div v-for="onerooms in 원룸들" :key="onerooms ">
  <img :src="onerooms.image" alt="" class="rom-img">
  <h4>{{onerooms.title}}</h4>
  <p>{{onerooms.price}}만원</p>
</div>


</template>

<script>
//import 작명 from './assets/oneroom.js';
//작명
// import {apple} from './assets/oneroom.js';
//apple

import data from './assets/oneroom';

export default {
  name: 'App',
  data(){ //data저장공간을 state라고 부름.
    return{
      원룸들 : data,
      모달창열림 : false,
      price1: 60,
      price2: 70,
      신고수:[0,0,0],
      fnt : 'color:blue',
      menus:['Home', 'Products', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구 원룸']
    }
  },
  methods:{
    increase(idx){
      this.신고수[idx] +=1;
    }
  },
  components: {
  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding:15px;
  border-radius: 5px;
}
.menu a{
  color:white;
  padding: 10px;
}
.rom-img{
  width: 100%;
  margin-top: 40px;
}
</style>
