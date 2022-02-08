<template>
  

<div>
  <img alt="Vue logo" src="./assets/logo.png">
  <div class='menu'>
    <a v-for="(menu,i) in menuATag" :key="i">{{menu}}</a>
  </div>
  
<div v-for="(item,i) in mockproductz" :key="i">
  <img :src="mockproductz[i].image"/>
  <h4>{{mockproductz[i].title}}</h4>
  <p>{{mockproductz[i].price}}</p>
  <button @click="showModal=!showModal" >ddddaclose modal</button>
</div>
<ModalExample what='snappleasdfasdfasdf' :whatev='products' />


 
  <div>
    <img src="./assets/room0.jpg" class="product-img">
    <h4>
      {{products[0]}}
    </h4>
    <p>${{ price2 }}</p>
    <button @click="increaseLike(0)">Like</button> <span>Liked: {{liked[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="product-img">
    <h4>
      {{products[1]}}
    </h4>
    <p>${{ price2 }}</p>
    <button @click="increaseLike(1)">Like</button> <span>Liked: {{liked[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="product-img">
    <h4>
      {{products[2]}}
    </h4>
    <p>${{ price2 }}</p>
    <button @click="increaseLike(2)">Like</button> <span>Liked: {{liked[2]}}</span>
  </div>
  </div>
</template>

<script>
import mockdata from './assets/mockprodcuts'
import ModalExample from './components/Modal.vue'
export default {
  name: 'App',
  data(){
    return {
      mockproductz: mockdata,
      showModal:false,
      liked:[0,0,0],
      price1: 600,
      price2: 1000,
      products : ['Durango', 'Rainbow', 'Buffalo'],
      menuATag : ['Home', 'Shop', 'About', 'Contact']
    }
  },
  methods :{
    increaseLike(i){
      this.liked[i]++;
    }
  },
  components: {
    ModalExample
  }
}
</script>

<style>
body {
  margin:0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width:100%; height:100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding:20px;
}
.white-bg {
  width:100%;
  background: white;
  border-radius: 8px;
  padding:20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius:5px;
}
.menu a {
  color:white;
  padding: 10px;
}
.product-img{
  width: 80%;
  margin-top: 40px;
}

</style>
