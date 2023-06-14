<template>
  <div class="menu">
    <img class="logo" src="./assets/logo.png" alt="">
    <a v-for="(menu, index) in menus" :key="index">{{menu}}</a>
  </div>

  <div class="content" v-for="(product, index) in data" :key="index">
    <div class="img_wrap">
      <img class="room-img" :src="product.image" alt="image" />
    </div>
    <h4>{{product.title}}</h4>
    <p>${{product.price}}</p>
  </div>
</template>

<script>
import roomdata from './roomdata'
export default {
  name: 'App',
  data() {
    return {
      menus: ['Home', 'Shop', 'About'],
      data : roomdata,
    }
  },
  methods: {
  }
}
</script>
<style>
h4{
  cursor: pointer;
}
button{
  border: 0 none;
  cursor: pointer;
}
#app {
  font-family: Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
/* 메뉴바 */
.logo{
  width: 35px;
  position: absolute;
  left: 10%;
  top: 5px;
}
.menu{
  margin: auto;
  background: darkslateblue;
  width: 100%;
  padding: 15px;
  border-radius: 5px;
  box-sizing: border-box;
  display: flex;
  justify-content: space-evenly;
  position: fixed;
  z-index: 1000;
}
.menu a{
  color: rgb(219, 213, 255);
  transition: all 0.5s;
  padding: 0 10px;
}
/* 메인 콘텐트 */ 
.content{
  padding-top: 48px;
}
.wrap{
  width: 100%;
  height: 100%;
  position: relative;
}
.room-img{
  width: 60%;
  transition: all 0.5s;
  position: relative;
}
</style>