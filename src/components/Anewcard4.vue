<template>
    <div class="box_all">
    <div class="col" v-for="(n,i) in travelList" :key="n">
      <div class="card" style="width: 25rem;" >
        <img :src="n.img" class="card-img-top">
        <div class="card-body">
          <h3 class="card-title">{{ n.name }}</h3>
          <p>ราคาโต๊ะ : {{n.price}}</p>
          <h6>*** จำกัด 1 คนต่อการจอง 1 โต๊ะ ***</h6>

          <a class="btn btn-primary" @click="list_local_control(i.name, i.quantity)"> จองโต๊ะ </a>
        </div>
      </div>
    </div>
  </div>

</template>

<script setup>

import { ref } from 'vue';

const travelList=ref([
{name:'คั่วไก่นิมมาน',     price:100, img:"https://cms.dmpcdn.com/food/2020/09/03/aec9bad0-edae-11ea-bbdd-775d9efe2958_original.jpg", quantity: 0 ,
    text_box:'ร้าน คั่วไก่นิมมาน ร้านอาหารจานด่วน สตรีทฟู้ดที่ต้องห้ามพลาดถ้าได้มาย่านนิมมานเหมินท์ จุดเด่นของคั่วไก่ร้านนี้คือความหอมกระทะที่ติดมากับตัวเส้นใหญ่เลย ยิ่งเสิร์ฟมาแบบกระทะร้อน จะยิ่งฟินมากขึ้น ! ส่วนเนื้อไก่ก็ใส่มาอย่างจัดหนัก จัดเต็มอีกด้วย อร่อยจริงไม่พูดเยอะ'
    },])


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