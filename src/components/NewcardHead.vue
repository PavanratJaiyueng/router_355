<template>
<div class="row mb-2">
        <div class="col-md-6" v-for="(n,i) in travelList" :key="n">
          <div class="row g-0 border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative">
            <div class="col p-4 d-flex flex-column position-static">
              <strong class="d-inline-block mb-2 text-primary-emphasis">ร้านที่ {{ i+1 }} </strong>
              <h3 class="mb-0">{{n.name}}</h3>
              <div class="mb-1 text-body-secondary">ราคาต่อโต๊ะ {{n.price}} บาท</div>
              <p class="card-text mb-auto">{{n.text_box}}</p>
              
              <div style="margin-bottom: 30px;">
              <RouterLink :to="{name: `news_${i+1}` , params: {id: n.name}}" class="icon-link gap-1 icon-link-hover stretched-link">
               กดดูรายละเอียดเพิ่มเติม
                <svg class="bi"> <use xlink:href="#chevron-right"/></svg>
             </RouterLink>
            </div>     
            </div>
            <div class="col-auto d-none d-lg-block">
              <svg class="bd-placeholder-img" width="200" height="250" xmlns="http://www.w3.org/2000/svg" role="img"  preserveAspectRatio="xMidYMid slice" focusable="false" 
              style="margin: 15px;" >
                <image :xlink:href="n.img" x="0" y="10" width="200" height="200" />
              </svg>
            </div>
          </div>
        </div>
    </div>
</template>

<script setup>

import { RouterLink } from 'vue-router'
import { ref } from 'vue';

const travelList=ref([
   {name: 'ต๋องเต็มโต๊ะ',  price:100, img:"https://cms.dmpcdn.com/food/2020/09/03/afc3d240-edae-11ea-bbdd-775d9efe2958_original.jpg", quantity: 0 ,
    text_box:'ร้านอาหารเหนือชื่อดังของเชียงใหม่ อย่างร้าน ต๋องเต็มโต๊ะ ร้านนี้เป็นร้านดังแห่งย่านนิมมานฯ อาหารเหนือของที่นี่มีให้เลือกทานหลายอย่าง รสชาติดีถูกปากทั้งคนท้องถิ่น และนักท่องเที่ยว และด้วยราคาที่เป็นกันเอง บรรยากาศร้านชิลๆ ถึงแม้ว่าจะมีลูกค้านั่งเต็มร้านทุกวัน บอกเลยว่าถ้าไปเชียงใหม่แล้วไม่เช็คอินที่ร้านนี้ก็เหมือนมาไม่ถึงนะจ๊ะ '
    }, 
  
    {name:'Papa Curry',    price:100, img:"https://cms.dmpcdn.com/food/2020/09/03/af234c80-edae-11ea-ac6b-db7ce016a443_original.jpg", quantity: 0 ,
    text_box:'Papa Curry ร้านข้าวแกงกะหรี่ญี่ปุ่นเจ้าดังของเชียงใหม่ ข้าวแกงกะหรี่ของที่นี่คือดีมากกกก กินแล้วว้าวแน่นอน ร้านนี้เป็นร้านเล็กๆ หลายๆคนอาจจะสงสัยว่าทำไมต้องไปกินข้าวแกงกะหรี่ถึงเชียงใหม่ แต่ถ้าได้ชิมรับรองว่าจะติดใจ ถ้ามาเชียงใหม่แล้วควรมาโดน!!'
    },
    
    {name:'ครัวอาจารย์สายหยุด',   price:100, img:"https://cms.dmpcdn.com/food/2022/12/02/d95c5540-725f-11ed-b6e3-7dc2b5c3a572_webp_original.jpg", quantity: 0 ,
    text_box:'ร้านอาหารไทยสารพัดเมนูจากทุกภาคของไทย ครัวอาจารย์สายหยุด สูตรอาหารของคุณแม่หมอทราย หรืออาจารย์สายหยุด ที่เป็นอดีตครูสอนทำอาหาร ตัวร้านจะดูเรียบง่าย บรรยากาศอบอุ่นเหมือนได้ทานอาหารที่บ้าน แต่ทุกเมนูพิถีพิถันอย่างประณีตสุดๆ ค่ะ ทำให้ทุกเมนูล้วนเป็นศิลปะการทำอาหารที่ทำให้บรรดานักชิมรู้สึกเหมือนอยู่ในวังเลยทีเดียว'
    },
    
    {name:'คั่วไก่นิมมาน',     price:100, img:"https://cms.dmpcdn.com/food/2020/09/03/aec9bad0-edae-11ea-bbdd-775d9efe2958_original.jpg", quantity: 0 ,
    text_box:'ร้าน คั่วไก่นิมมาน ร้านอาหารจานด่วน สตรีทฟู้ดที่ต้องห้ามพลาดถ้าได้มาย่านนิมมานเหมินท์ จุดเด่นของคั่วไก่ร้านนี้คือความหอมกระทะที่ติดมากับตัวเส้นใหญ่เลย ยิ่งเสิร์ฟมาแบบกระทะร้อน จะยิ่งฟินมากขึ้น ! ส่วนเนื้อไก่ก็ใส่มาอย่างจัดหนัก จัดเต็มอีกด้วย อร่อยจริงไม่พูดเยอะ'
    },
    
    {name:'สุกี้ช้างเผือก',  price:100, img:"https://cms.dmpcdn.com/food/2022/12/03/310ae600-7263-11ed-b6e3-7dc2b5c3a572_webp_original.jpg", quantity: 0 ,
    text_box:'อีกหนึ่งร้านสตรีทฟู้ดเจ้าดังของเชียงใหม่ ร้านสุกี้ช้างเผือก สาขาแรกเริ่มอยู่ในตลาดโต้รุ่งช้างเผือก บอกเลยว่าเอาใจคนนอนดึกแบบสุดๆ เพราะเค้าเปิดายถึงเที่ยงคืนกันเลยทีเดียว ความเด็ดของสุกี้ร้านนี้คือ สุกี้แห้งหอมกลิ่นกระทะ ใส่เครื่องมาแบบจัดเต็ม ในราคาเบาๆ บอกเลยว่าเด็ดต้องโดน '
    },
    
    {name:'Khao-Sō-i ข้าวโซอิ',  price:100,  img:"https://cms.dmpcdn.com/food/2022/12/03/4c892380-7266-11ed-bada-27675389f76f_webp_original.jpg", quantity: 0 ,
    text_box:'Khao-Sō-i ข้าวโซอิ ร้านข้าวซอยเส้นสด ใครชอบทานข้าวซอยน้ำซุปเข้มข้น เส้นหนึบหนับ เมนูที่ต้องโดนคือ ข้าวซอยเส้นสดไก่โซอิ และข้าวซอยผัดแห้ง บอกเลยว่าอร่อยเข้มข้น ซุปอร่อย เส้นดี รสชาติโดนใจ แถมร้านยังสวยให้ฟีลญี่ปุ่นไปอีก เรียกได้ว่าเป็นการทานข้าวซอยในรูปแบบที่แตกต่างออกไปได้เลย'
    },
])


</script>

<style>
  .row {
    background-color: #f5f5f5; 
  }

  h3 {
    color: #333; 
  }
  .row {
    background-color: #f5f5f5;
    padding: 20px;
    margin-bottom: 20px; 
  }

  h3 {
    color: #333;
    font-size: 24px; 
  }

  .row {
    background-color: #f5f5f5;
    padding: 20px; 
  }

  h3 {
    color: #333;
    font-size: 24px;
  }

  .icon-link {
    text-decoration: none; 
    color: #007bff;
    transition: color 0.2s;
  }

  .icon-link:hover {
    color: #0056b3; 
  }
  
  .shadow-box {
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.2); 
  }


</style>

