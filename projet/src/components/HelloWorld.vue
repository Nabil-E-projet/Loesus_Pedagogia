
<template>
  <div class="hello">
    <div :key="index" v-for="(prodFake, index) in (prodFake)" >
      <h1>Nom du produit : <br> {{ prodFake.title}}</h1>
      <img :src="prodFake.image" alt="">
      <h1>Prix du produit : {{ prodFake.price}}€</h1>
      <h1>Description:</h1>
      <h2>{{ prodFake.description}}</h2>
    </div>
  </div>
</template>

<script>
import './style.css'
  import axios from 'axios'
  export default {
    name: 'HelloWorld',
    data(){
      return{
        prodFake: null,
      }
    },
    mounted(){
      axios
      .get('https://fakestoreapi.com/products')
      .then((reponse) => {
        this.prodFake = reponse.data;
        console.log(this.prodFake)
      });
    }
  }
</script>

<style scoped>

</style>
