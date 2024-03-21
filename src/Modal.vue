<template>
  <div class="black-bg " v-if="모달창열렸니==true">
  <div class="white-bg">
    <img :src="원룸들[누른거].image" class="room-img2">
    <h4>{{원룸들[누른거].title}}</h4>
    <p>{{원룸들[누른거].content}}</p>
    <p> {{month}}개월선택함 : {{원룸들[누른거].price * month}}</p>
    <!-- <input @input="month = $event.target.value"> -->
    <input v-model="month" @keydown.space.prevent>
     <button @click="$emit('closeModal')">닫기</button> 
  </div>
  </div>
</template>

<script>
export default {
    name : 'Modal',
    data() {
    return {
      month : 1,
     }
    },
    watch : {
    month(a){
      if (isNaN(a) == true || a >= 13){
        if(isNaN(a)) {
      alert('문자입력하지마라');    
      } else {
        alert('13이상입력 ㄴㄴ')
      }
      this.month = 1;
      }
    },
 },

//  mounted() {
//   // 숫자 입력 필드에 대한 keydown 이벤트를 추가하여 스페이스바 입력을 막습니다.
//   document.getElementById('numericInput').addEventListener('keydown', function(event) {
//     // 키코드 32는 스페이스바입니다. 스페이스바 입력을 막습니다.
//     if (event.keyCode === 32) {
//       event.preventDefault();
//     }
//   });
// },

    props : {
        원룸들 : Array,
        누른거 : Number,
        모달창열렸니: Boolean,
    },

    beforeUpdate() {
    if (this.month == 2) {
      this.month = 3; 
      alert('2를 입력했습니다.');
    }
  } 
}
</script>

<style>

</style>