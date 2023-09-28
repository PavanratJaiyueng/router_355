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
    {name:'ครัวอาจารย์สายหยุด',   price:100, img:"https://cms.dmpcdn.com/food/2022/12/02/d95c5540-725f-11ed-b6e3-7dc2b5c3a572_webp_original.jpg", quantity: 0 ,
    text_box:'ร้านอาหารไทยสารพัดเมนูจากทุกภาคของไทย ครัวอาจารย์สายหยุด สูตรอาหารของคุณแม่หมอทราย หรืออาจารย์สายหยุด ที่เป็นอดีตครูสอนทำอาหาร ตัวร้านจะดูเรียบง่าย บรรยากาศอบอุ่นเหมือนได้ทานอาหารที่บ้าน แต่ทุกเมนูพิถีพิถันอย่างประณีตสุดๆ ค่ะ ทำให้ทุกเมนูล้วนเป็นศิลปะการทำอาหารที่ทำให้บรรดานักชิมรู้สึกเหมือนอยู่ในวังเลยทีเดียว'
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
  