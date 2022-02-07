<template>
  
<div>
<div>
  this is modal
  <button @click="showModal=!showModal" >show modal</button><p>{{what}}</p>
  <p v-for="(item,i) in whatev" :key='i'>{{item}}</p>
  <p>{{whatev}}</p>
  <div class='menu'>
    <a v-for="(menu,i) in menuATag" :key="i">{{menu}}</a>
  </div>
<div v-for="(item,i) in mockproductz" :key="i">
  
  <img :src="mockproductz[i].image"/>
  <h4>{{mockproductz[i].title}}</h4>
  <p>{{mockproductz[i].price}}</p>
  <button @click="showModal=!showModal" >close modal</button>
</div>
</div>
</div>


  
</template>

<script>

export default {
  props:["what","whatev"],
  name: 'App',
  data(){
    return {
      
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

