<template>

  <div class="black-bg">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, index) in menus" :key="index">{{menu}}</a>
  </div>

  <div v-for="(product, index) in products" :key="index">
    <img class="room-img" :src="product.imgSrc" alt="image" />
    <h4>{{product.name}}</h4>
    <p>{{product.price}}</p>
    <div class="report-box">
      <span>신고수 : {{product.fakeReport}}</span>
      <button @click="reportFakeProduct(index)">허위매물신고</button> 
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      menus: ['Home', 'Shop', 'About'],
      products : [
        {name: '역삼동 원룸', price: '70만원', fakeReport: 0, imgSrc: require('./assets/images/room0.jpg')},
        {name: '천호동 원룸', price: '50만원', fakeReport: 0, imgSrc: require('./assets/images/room1.jpg')},
        {name: '마포구 원룸', price: '60만원', fakeReport: 0, imgSrc: require('./assets/images/room2.jpg')},
      ]
    }
  },
  methods: {
    reportFakeProduct(num) {
      this.products[num].fakeReport = this.products[num].fakeReport + 1;
    }
  },  
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
/* 모달창 */ 
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
  display: none;
}
.white-bg{
  width: 50%;
  background: #fff;
  border-radius: 8px;
  padding: 20px;
}

/* 메뉴바 */
.menu{
  margin: auto;
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
  box-sizing: border-box;
  display: flex;
  justify-content: space-evenly;
}
.menu a{
  color: rgb(219, 213, 255);
  transition: all 0.5s;
  padding: 0 10px;
}
.menu a:hover{
  color: white;
  text-shadow: 2px 2px 2px rgb(154, 137, 255);;
}
/* 메인 콘텐트 */ 
.report-box{
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
}
.report-box button{
  background: rgb(219, 213, 255);
  color: darkslateblue;
  padding: 10px 5px;
  font-size: 14px;
  border: 0 none;
  border-radius: 12px;
  cursor: pointer;
  margin-left: 15px;
  transition: all 0.5s;
}
.report-box button:hover{
  background: darkslateblue;
  color: rgb(219, 213, 255);
}
.report-box span{
  background: darkslateblue;
  color: rgb(219, 213, 255);
  padding: 10px 5px;
  font-size: 14px;
  border: 0 none;
  border-radius: 12px;
}
.room-img{
  width: 60%;
  transition: all 0.5s;
}
.room-img:hover{
  filter:brightness(70%)
}
</style>