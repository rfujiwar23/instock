<template>
  
    <div class="card" v-for="(item, index) in items" :key='index'>
      <div v-if="item.instock === true">
         In Stock
       </div>
      <div v-else class="gray">
         Out of Stock
       </div>
       <div>
         <img :src="item.img" :alt="item.name">
       </div>
       <div class="card-body">
         <h2> {{item.name}}</h2> 
         <p>{{item.price}}円</p>
         <p>税込 {{ (item.price * 1.1).toFixed() }}円</p> 
       </div> 
    </div>


</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      items: [
        {name: 'TOKIO', price: 3000, instock: true, img: 'https://res.cloudinary.com/rfujiwar23/image/upload/v1604973019/oway/shaving_cream.jpg'},
        {name: 'OWAY', price: 2700, instock: false},
        {name: 'LIKE', price: 4000, instock: true},
      ],
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
  /* color: green; */
  margin-top: 60px;
}

.card {
  border:1px solid #9a9a9a;
  width:30%;
  position:relative;
  margin:3vh auto;
}

.gray {
  position:absolute;
  background-color: #9a9a9a;
  height:100%;
  width:100%;
  opacity:0.5;
  color: red;
  font-weight:bold;
}
</style>
