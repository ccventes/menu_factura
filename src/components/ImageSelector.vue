<script  lang="ts">
import { RouterLink, RouterView } from 'vue-router'

import { defineComponent, ref } from 'vue'

interface Iimage {
  imageUrl: String,
  caption:  String,
  valor : number
  isActive: boolean,
  zindex: number
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
          zindex: 1,
          
        },
        {
          imageUrl: './src/images/imagen2.jpg',
          caption: 'Photo by 2',
          valor : 1,
          isActive: false,
          zindex: 1,

        },
        {
          imageUrl: 'src/images/imagen3.jpg',
          caption: 'Photo by 3',
          valor : 1,
          isActive: false,
          zindex: 1,

        },
        {
          imageUrl: "src/images/imagen1.jpg",
          caption: 'Photo by 4',
          valor : 1,
          isActive: false,
          zindex: 1,

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
          image.zindex = -1;
        }
        else{

          image.valor = 1;
          image.zindex = 1;
        }
        
        
        


       },

    },

});








</script>

<template>
  
  <div class="image-container">
  <!-- Inserta tus URLs de imágenes aquí -->
  <!-- Use v-for to iterate over each item in the array -->
  

  
  
  <!-- Añade más imágenes según sea necesario -->

  <div class="grid-item" @click="select_image(image)" v-for="(image,index) in images" :key=index>
       <img    :src=image.imageUrl alt="vue" :style="{  opacity : image.valor, zIndex : image.zindex}"> 
       <div class="info-texto">cambio el texto

        <button class = "Expander"> Expandir </button>
       </div>
       <h3>{{image.caption}}</h3>
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
  flex-direction: column;
  border-radius: 25px;
  border: 2px none #191a18;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  padding: 20px;
  width: 200px;
  height: 150px;
  width: 250px;
  height: auto;
  margin: 5px;
  

}

.image-container img{

  
  width: 200px; /* Set your desired width */
  height: auto; /* Maintain the aspect ratio */
  border-radius: 15px;
  margin-bottom: 20px;
  margin-right: 0px;
  transition: opacity 0.5s;
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

.Expander{

    margin-top: 130px;
    z-index: 2;

}
</style>
