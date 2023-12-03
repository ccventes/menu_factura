<script  lang="ts">
import { RouterLink, RouterView } from 'vue-router'

import { defineComponent } from 'vue'


export default defineComponent({
    data(){

        return{
            images:[{
          imageUrl: 'src/images/imagen1.jpg',
          caption: 'Photo by 1'
        },
        {
          imageUrl: 'src/images/imagen2.jpg',
          caption: 'Photo by 2'
        },
        {
          imageUrl: 'src/images/imagen3.jpg',
          caption: 'Photo by 3'
        },
        {
          imageUrl: "src/images/imagen1.jpg",
          caption: 'Photo by 4'
        }], 

        };

    },

});




</script>

<template>
  <h1>Hola mundo</h1>
  <div class="image-container">
  <!-- Inserta tus URLs de imágenes aquí -->
  <!-- Use v-for to iterate over each item in the array -->
  <img v-for="(image,index) in images" :key=index :src=image.imageUrl alt="Image"> 

  
  <img src="./images/imagen1.jpg" alt="Imagen 1">
  <img src="./images/imagen2.jpg" alt="Imagen 2">
  <img src="./images/imagen3.jpg" alt="Imagen 3">
  <!-- Añade más imágenes según sea necesario -->

  <div class="grid-item">
       <img src="./images/imagen1.jpg" alt="Image 1"> 
       <div class="info-texto">texto</div>
  </div>
  <div class="grid-item">
      
      <img src="./images/imagen2.jpg" alt="Image 1">  
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
  opacity: 0.5;

}

.image-container img{

  
  width: 200px; /* Set your desired width */
  height: auto; /* Maintain the aspect ratio */
  border-radius: 15px;
  margin-bottom: 20px;
  margin-right: 20px;
}

img:hover {
  transform: scale(1.3); /* Increase size on hover */
}
.info-texto{
  position: absolute;
  top: -50%;
  left: 0%;
}
/*
.intem-info{
  margin: 0;
  padding: 0;
  position: absolute;
  
  width: 50px; /* Set your desired width */
  /*height: auto; /* Maintain the aspect ratio */
  
  /*color: white;
  opacity: 0;
  transition: opacity 0.3s; /* Add a smooth transition effect */
  /*top: 50%;
  left: 50%;
  z-index: 2 ;
}

/*/
</style>
