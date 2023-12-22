<script  lang="ts">
import { RouterLink, RouterView } from 'vue-router'


import { defineComponent, ref } from 'vue'

interface Iimage {
  imageUrl: String,
  caption:  String,
  valor : number
  isActive: boolean,
  zindex: number,
  isButtonDisabled : boolean
}

interface IFoodInfo{
  price:  number,
  description: String,
  Modifications: String,
  CookTime: number,
  Category: String

}

interface Ibutton{

    message: String
    show: boolean
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
          isButtonDisabled : true,
          foodInfo : {
            price : 50000,
            description :  'sopa de verengena con crema imagineu',
            Modifications: '',
            CookTime: 30,
            Category: ''
          },
          button :{

            message: 'Expander',
            show: true,
          }
          
        },
        {
          imageUrl: './src/images/imagen2.jpg',
          caption: 'Photo by 2',
          valor : 1,
          isActive: false,
          zindex: 1,
          isButtonDisabled : true,
          foodInfo : {
            price : 70000,
            description :  'pasta alfredo con pollo teriyaki',
            Modifications: '',
            CookTime: 30,
            Category: ''
          },
          button :{

              message: 'Expander',
              show: true,
          }

        },
        {
          imageUrl: 'src/images/imagen3.jpg',
          caption: 'Photo by 3',
          valor : 1,
          isActive: false,
          zindex: 1,
          isButtonDisabled : true,
          foodInfo : {
            price : 90000,
            description :  'sho que se che',
            Modifications: '',
            CookTime: 30,
            Category: ''
          },
          button :{

              message: 'Expander',
              show: true,
          }

        },
        {
          imageUrl: "src/images/imagen1.jpg",
          caption: 'Photo by 4',
          valor : 1,
          isActive: false,
          zindex: 1,
          isButtonDisabled : true,
          foodInfo : {
            price : 120000,
            description :  'Por que hice tanta comida?',
            Modifications: '',
            CookTime: 30,
            Category: ''
          },
          button :{

            message: 'Expander',
            show: true,
          }

        }], 

        };

    },
    methods: {
       select_image(image: Iimage){
        console.log( `Image clicked`);
        console.log(image)
        image.isActive = !image.isActive;
        if(image.isActive === true){

          image.valor = 0.0;
          image.zindex = -1;
        }
        else{

          image.valor = 1;
          image.zindex = 1;
          image.isButtonDisabled = true;
        }
       },
       click_button : function(button: Ibutton){
        //targets: this.$refs.square,
        //translateX: 500
        button.message = "click"
        button.show = false
        console.log("Click exclusivamente al boton")
        console.log("debe mostrarse la barra? ", !button.show)
        


        

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
       <img    :src=image.imageUrl alt="vue" :style="{  opacity : image.valor, zIndex : image.zindex }"> 
       <div class="info-texto" >cambio el texto
       </div>
       <Transition name = "fade">
       <button v-if = "image.button.show" class = "Expander" @click = "click_button(image.button)" > {{ image.button.message }} </button>
      </Transition>
      <Transition name = "Progress" >
      <div v-if = "!image.button.show" class = "Progress-box">
        
         <Transition name = "percentage"  appear>
          <div v-if = "!image.button.show" class="myBar"></div>
         </Transition>
      </div>
    </Transition>   
    <h3>{{image.caption}}</h3>
   <!-- <svg width="100" height="100"><circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" /></svg> -->
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

    position:absolute;
    margin-top: 130px;
    z-index: 3; /*No te olvides modi*/ 
    font-size: 14px;
}

.fade-leave-active{
  animation: fade-out 0.5s;

}

@keyframes fade-out{

   0% {
      opacity: 1;
   }
   50% {
      opacity: 0.5;
   }
   100% {
      opacity: 0;
   }

}

/*Para la animacion myProgress debe cambiar del ancho actual a  60% */ 


/*empezando en ancho 0% y alto 30px Para la animacion myBar debe cambiar del Alto  actual a  10px */



.myBar {
  width: 100%;
  height: 10px;
  background-color: #04AA6D;
  text-align: center;
  line-height: 30px;
  color: white;
   
}
.percentage-enter-active{

    animation: expand 2s ease;
}
.percentage-leave-active{

  animation: expand 2s ease;
}
@keyframes expand{
  0% {
    width: 0%;
    height: 30px;
    background-color: #04AA6D;
    text-align: center;
    line-height: 30px;
    color: white;
  }
  1% {
    width: 1%;
    height: 10px;
    background-color: #04AA6D;
    text-align: center;
    line-height: 30px;
    color: white;
  }
  

  
  100%{
    width: 100%;
    height: 10px;
    background-color: #04AA6D;
    text-align: center;
    line-height: 30px;
    color: white;

  }
}
/*
id="myProgress"
       
        id="myBar"
*/
.Progress-box{ /* Este es el estado final*/ 
  width: 60%;
  background-color: #ddd;
  position: absolute;
  transform: translateY(65px);
  opacity: 1;
}



.Progress-enter-from { /* Este es el estado inicial*/ 
  width: 30%;
  background-color: #ddd;
  position: absolute;
  transform: translateY(65px);
  opacity: 1;
}
.Progress-enter-to{ /*Este es el estado final*/ 

  background-color: #ddd;
  position: absolute;
  transform: translateY(65px);
  opacity: 1;
  width: 60%;  
}
.Progress-enter-active{/*Esta es la transción aqui se dice cuanto dura*/

  transition: all 1s;
}
.Progress-leave-from { /* Este es el estado inicial*/ 
  width: 30%;
  background-color: #ddd;
  position: absolute;
  transform: translateY(65px);
  opacity: 1;
}
.Progress-leave-to{ /*Este es el estado final*/ 

background-color: #ddd;
position: absolute;
transform: translateY(65px);
opacity: 1;
width: 60%;  
}

.Progress-leave-active{/*Esta es la transción aqui se dice cuanto dura*/

transition: all 1s;
}
/*

No olvides las leave cuando lleguemos a la siguiente parte
/*
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}

@keyframes bounce {
  0% {
    width: 30%;
  }
  50% {
    width: 45%;
  }
  100% {
    width: 60%;
  }
}
*/





</style>
