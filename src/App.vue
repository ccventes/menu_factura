<script  lang="ts">
import { RouterLink, RouterView } from 'vue-router'

import { defineComponent, ref } from 'vue'

interface Iimage {
  imageUrl: String,
  caption:  String,
  valor : number
  isActive: boolean
}
export default defineComponent({
    data(){

        return{
        isActive: false,
        images:[{
          imageUrl: 'src/images/imagen1.jpg',
          caption: 'Photo by 1',
          valor : 1,
          isActive: false,
          
        },
        {
          imageUrl: 'src/images/imagen2.jpg',
          caption: 'Photo by 2',
          valor : 1,
          isActive: false,
        },
        {
          imageUrl: 'src/images/imagen3.jpg',
          caption: 'Photo by 3',
          valor : 1,
          isActive: false,
        },
        {
          imageUrl: "src/images/imagen1.jpg",
          caption: 'Photo by 4',
          valor : 1,
          isActive: false,
        }], 

        };

    },
    methods: {
       select_image(image: Iimage){
        console.log( `Image clicked`);
        console.log(image)
        image.isActive = !image.isActive;
        if(image.isActive === true){

          image.valor = 0.3;
        }
        else{

          image.valor = 1;
        }
        
        
        


       },

    },

});








</script>

<template>
  <h1>Hola mundo</h1>
  <div class="image-container">
  <!-- Inserta tus URLs de imágenes aquí -->
  <!-- Use v-for to iterate over each item in the array -->
  

  
  
  <!-- Añade más imágenes según sea necesario -->

  <div class="grid-item" v-for="(image,index) in images" :key=index>
       <img  @click="select_image(image)"  :src=image.imageUrl alt="vue" :style="{  opacity : image.valor}"> 
       <div class="info-texto">cambio el texto</div>
  </div>


</div>
</template>

<style scoped>


.image-container{

    width: 800px; /* Set your desired width */
    height: auto; /* Maintain the aspect ratio */
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    
}
.grid-item{
  
  position: relative;
  display:flex;
  align-items: center;
  justify-content: center;
  

}

.image-container img{

  
  width: 200px; /* Set your desired width */
  height: auto; /* Maintain the aspect ratio */
  border-radius: 15px;
  margin-bottom: 20px;
  margin-right: 20px;
  transition: opacity 2s;
  opacity: 1;
  
}


.active{

  opacity:  0.3;
}
.info-texto{
  position: absolute;

  z-index: -1;
  font-family: Montserrat;
  font-weight: bold;
  font-size: 20px;
  
  width: 80%;
  height: 80%;
  
  
}
.info-texto:hover{
  z-index: 1;
  font-family: Montserrat;
  font-weight: bold;
  font-size: 20px;
  
  

}
@font-face {
    font-family: Montserrat;
    src: url('~@/assets/fonts/Montserrat/static/Montserrat-Bold.ttf');
}





</style>
