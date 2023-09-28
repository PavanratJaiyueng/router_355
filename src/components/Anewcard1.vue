<template>
  <div class="box_all">
    <div class="col" v-for="(n, i) in travelList" :key="n">
      <div class="card">
        <img :src="n.img" class="card-img-top" alt="Travel Destination">
        <div class="card-body">
          <h3 class="card-title">{{ n.name }}</h3>
          <p class="card-text">ราคาโต๊ะ: {{ n.price }} บาท</p>
          <h6 class="card-subtitle">*** จำกัด 1 คนต่อการจอง 1 โต๊ะ ***</h6>
          <button class="btn btn-primary" @click="list_local_control(n.name, n.quantity)">จองโต๊ะ</button>
        </div>
      </div>
    </div>
  </div>
</template>


<script setup>

import { ref } from 'vue';

const travelList=ref([
{name: 'ต๋องเต็มโต๊ะ',  price:100, img:"https://cms.dmpcdn.com/food/2020/09/03/afc3d240-edae-11ea-bbdd-775d9efe2958_original.jpg", quantity: 0 ,
    text_box:'ร้านอาหารเหนือชื่อดังของเชียงใหม่ อย่างร้าน ต๋องเต็มโต๊ะ ร้านนี้เป็นร้านดังแห่งย่านนิมมานฯ อาหารเหนือของที่นี่มีให้เลือกทานหลายอย่าง รสชาติดีถูกปากทั้งคนท้องถิ่น และนักท่องเที่ยว และด้วยราคาที่เป็นกันเอง บรรยากาศร้านชิลๆ ถึงแม้ว่าจะมีลูกค้านั่งเต็มร้านทุกวัน บอกเลยว่าถ้าไปเชียงใหม่แล้วไม่เช็คอินที่ร้านนี้ก็เหมือนมาไม่ถึงนะจ๊ะ '
    }])


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