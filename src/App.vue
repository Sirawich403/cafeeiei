<template>
  <div class="coffee-shop-app">
    <h1>ร้านคาเฟ่<br> 
    กรุณาเลือกร้านที่ต้องการจอง</h1>
    <div class="coffee-shops">
      <div v-for="(shop, index) in coffeeShops" :key="index" class="coffee-shop">
        <h2>{{ shop.name }}</h2>
        <p>{{ shop.description }}</p>
        <img src="/download.jpg" class="card-img-top" alt="/download.jpg"><br><br>
        <button @click="reserveTable(shop)">จองโต๊ะ</button><bt></bt>
      </div>
    </div>

    <div v-if="reservation" class="reservation-details">
      <h2>ข้อมูลการจอง</h2>
      <p><strong>ชื่อ:</strong> {{ reservation.name }}</p>
      <p><strong>เบอร์โทร:</strong> {{ reservation.phone }}</p>
      <p><strong>วันที่:</strong> {{ reservation.date }}</p>
      <p><strong>เวลา:</strong> {{ reservation.time }}</p>
      <p><strong>จำนวนโต๊ะ:</strong> {{ reservation.tableCount }}</p>
    </div>
  </div>
</template>


<script>

export default {
  data() {
    return {
      coffeeShops: [
        {
          name: ' Yelloo ',
          description: 'คาเฟ่สไตล์มินิมอลเปิดใหม่ในเครือ Yellow Crafts Cafe ตัวร้านนั้นตั้งอยู่บนถนนนิมมานเหมินทร์ ฝั่งตรงข้ามวันนิมมาน'
          
        },
        {
          name: 'Groon',
          description: 'คาเฟ่เชียงใหม่ ที่ถ่ายรูปสวยแทบทุกมุม ตัวร้านตั้งอยู่แถวถนนสิริมังคราจารย์ เน้นขายขนมปังทำสดใหม่เป็นหลัก'
        },
        {
          name: ' Chom Cafe & Restaurant ',
          description: 'คาเฟ่ในจังหวัดเชียงใหม่อีกหนึ่งที่ที่มีบ่อปลาคาร์ปและไอน้ำคล้ายกับหมอกจางๆ บรรยากาศของร้านเหมือนกับหลุดเข้าไปในป่าที่เต็มไปด้วยต้นไม้และเฟิร์นสีเขียวมากมาย'
          

        },
        {
          name: 'Ei-Shin Bar & Cafe',
          description: 'ร้านอาหารกึ่งคาเฟ่สไตล์ญี่ปุ่นในสวนสวยใจกลางเมืองเชียงใหม่ จุดเด่นของร้านคือบรรยากาศดี ตกแต่งร้านสไตล์ญี่ปุ่น มีชุดกิโมโนให้ยืมเช่าถ่ายรูป'
        }
      ],
      reservation: null
    };
  },
  methods: {
    reserveTable(shop) {
      const name = prompt('กรุณากรอกชื่อ:');
      const phone = prompt('กรุณากรอกเบอร์โทร:');
      const date = prompt('กรุณาระบุวันที่:');
      const time = prompt('กรุณาระบุเวลา:');
      const tableCount = parseInt(prompt('กรุณาระบุจำนวนโต๊ะ:'));

      if (name && phone && date && time && tableCount > 0) {
        this.reservation = {
          name,
          phone,
          date,
          time,
          tableCount
        };
      } else {
        alert('กรุณากรอกข้อมูลให้ครบถ้วน');
      }
    }
  }
};
</script>

<style scoped>
.coffee-shop-app {
  flex: auto;
  text-align: center;
  font-family: Arial, sans-serif;
  background-color: #fffae9; /* Updated background color */
  padding: 232px;
}

h1 {
  color: #000000; /* White text color */
}

h3 {
  color: #ffedd1; /* Light gray text color for instructions */
}

.coffee-shops {
  background-image: url(C:\Users\eyhun\vite-project\chom.jpg);
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  
}

.coffee-shop {
  flex: auto;
  border: 1px solid #e7e7e7;
  background-color: #dce1ff;
  padding: 80px;
  margin: 80px;
  border-radius: 8px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  opacity: 0.9;
  filter: alpha(opacity=60); /* For IE8 and earlier */
}

button {
  background-color: #00ff6a;
  color: #fff;
  border: none;
  padding: 8px 16px;
  cursor: pointer;
  border-radius: 4px;
  transition: background-color 0.3s;
  
}

button:hover {
  background-color: #fff6a7;
}

.reservation-details {
  flex: auto;
  margin-top: 20px;
  padding: 20px;
  background-color: #cffdca;
  border-radius: 8px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}
h1,h3 {margin: 30px;
  background-color: #fffeb3;
  border: 5px solid rgb(255, 244, 244);
  opacity: 0.8;
  filter: alpha(opacity=60); /* For IE8 and earlier */
}

div.transbox p {
  margin: 5%;
  font-weight: bold;
  color: #000000;
}

</style>