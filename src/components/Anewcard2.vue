<template>
  <div class="box_all">
    <div class="col" v-for="(destination, index) in travelList" :key="index">
      <div class="card">
        <img :src="destination.img" class="card-img-top" alt="Travel Destination">
        <div class="card-body">
          <h3 class="card-title">{{ destination.name }}</h3>
          <p class="card-text">ราคาโต๊ะ: {{ destination.price }} บาท</p>
          <h6 class="card-subtitle">*** จำกัด 1 คนต่อการจอง 1 โต๊ะ ***</h6>

          <button class="btn btn-primary" @click="reserveTable(destination.name, destination.quantity)">จองโต๊ะ</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

import { ref } from 'vue';

const travelList = ref([
{name:'Papa Curry',    price:100, img:"https://cms.dmpcdn.com/food/2020/09/03/af234c80-edae-11ea-ac6b-db7ce016a443_original.jpg", quantity: 0 ,
    text_box:'Papa Curry ร้านข้าวแกงกะหรี่ญี่ปุ่นเจ้าดังของเชียงใหม่ ข้าวแกงกะหรี่ของที่นี่คือดีมากกกก กินแล้วว้าวแน่นอน ร้านนี้เป็นร้านเล็กๆ หลายๆคนอาจจะสงสัยว่าทำไมต้องไปกินข้าวแกงกะหรี่ถึงเชียงใหม่ แต่ถ้าได้ชิมรับรองว่าจะติดใจ ถ้ามาเชียงใหม่แล้วควรมาโดน!!'
    },
]);

</script>


<style scoped>
.card {
  width: 18rem;
  margin: 20px;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.card-img-top {
  height: 200px;
  object-fit: cover;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}

.card-body {
  padding: 20px;
}

.card-title {
  font-size: 1.5rem;
  margin-bottom: 10px;
}

.card-text {
  font-size: 1.2rem;
}

.card-subtitle {
  font-size: 1rem;
  color: #888;
  margin-top: 10px;
}

.btn-primary {
  background-color: #007BFF;
  border: none;
  border-radius: 5px;
  color: #fff;
}

.btn-primary:hover {
  background-color: #0056b3;
}

.box_all {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  margin: 30px auto;
}
</style>