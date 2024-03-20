<template>


<Modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" @closeModal="모달창열렸니 = false"/>


 <div class="menu">
  <a v-for="a in 메뉴들" :key="a">{{ a }}</a>
  <!-- <a>Products</a>
  <a>About</a> -->
 </div>




<!-- <div v-if="1 == 2">
  안녕하세요
</div>
<div v-else-if="1 ==3">
  안녕하세요2
</div> -->

  <img alt="Vue logo" src="./assets/logo.png">
 
   <Discount/>
 <!-- <div>
  <img :src="원룸들[0].image" class="room-img">
  <h4 @click="모달창열렸니 = true">{{원룸들[0].title}}</h4>
  <p>{{ 원룸들[0].price}}만원</p>
  <button @click="신고수[0]+=1">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
 </div>

 <div>
  <img :src="원룸들[1].image" class="room-img">
  <h4 @click="모달창열렸니 = true">{{원룸들[1].title}}</h4>
  <p>{{ 원룸들[1].price}}만원</p>
  <button @click="신고수[0]+=1">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
 </div>
 <div>
  <img :src="원룸들[2].image" class="room-img">
  <h4 @click="모달창열렸니 = true">{{원룸들[2].title}}</h4>
  <p>{{ 원룸들[2].price}}만원</p>
  <button @click="신고수[0]+=1">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
 </div>
 <div>
  <img :src="원룸들[3].image" class="room-img">
  <h4 @click="모달창열렸니 = true">{{원룸들[3].title}}</h4>
  <p>{{ 원룸들[3].price}}만원</p>
  <button @click="신고수[0]+=1">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
 </div>
 <div>
  <img :src="원룸들[4].image" class="room-img">
  <h4 @click="모달창열렸니 = true">{{원룸들[4].title}}</h4>
  <p>{{ 원룸들[4].price}}만원</p>
  <button @click="신고수[0]+=1">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
 </div>
 <div>
  <img :src="원룸들[5].image" class="room-img">
  <h4 @click="모달창열렸니 = true">{{원룸들[5].title}}</h4>
  <p>{{ 원룸들[5].price}}만원</p>
  <button @click="신고수[0]+=1">허위매물신고</button>
  <span>신고수 : {{신고수[0]}}</span>
 </div> -->



  <!-- 반복문 하는법
  <div  v-for="(b,i) in 건물이름" :key="i">
     <h4>{{ b }}</h4>
     <p>{{ price[i]}}만원</p>
  </div> -->
<!-- 
 <div v-for="(a,i) in 원룸들" :key="i">
  <img :src="원룸들[i].image" class="room-img">
  <h4 @click="모달창열렸니 = true; 누른거 = i">{{원룸들[i].title}}</h4>
  <p>{{ 원룸들[i].price}}만원</p>
 </div> -->


 <!-- <Card @openModal="모달창열렸니 = true" :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명"/> -->
 
<Card @openModal="모달창열렸니 = true; 누른거 = $event" :원룸들="원룸들[i]"   v-for="(작명,i) in 원룸들" :key="작명"/>
  
</template>

<script>


import data from './data.js';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import card from './card.vue';

export default {
  name: 'App',
  data() {
    return {    
      스타일: 'color: blue',
      메뉴들: ['Home', 'Products', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      price: ['50', '60', '70'],
      신고수: [0, 0, 0],
      모달창열렸니: false,
      원룸들 : data,
      누른거 : 0,
    }
  },

  methods: {
    // increase() {
    //   신고수 += 1;
    // }
  },

  components: {
    Discount : Discount,
    Modal : Modal,
    Card : card,
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}           
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width:100%;
  margin-top: 40px;
}
.body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; 
  background: white;
  border-radius: 8px; padding: 20px;
}
.room-img2 {
  width:50%;
  margin: 40px;
}

</style>
