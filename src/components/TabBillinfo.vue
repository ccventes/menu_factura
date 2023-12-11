<script  lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({

    
})

</script>

<template>
    
    <div class="container-tab"> 

        <div class = "tab"> Tab  </div>
        <div class = "tab"> Tab  </div>
        <div class = "tab"> Tab  </div>
        <div class = "tab"> Tab  </div>
    
    </div>
    
</template>

<style scoped>
.container-tab {

    
    width: 1000px;
    height: auto;
    border-radius: 5px;
    border: 2px none #191a18;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    display:flex;
    
    
    flex-direction: column;
    
}

.tab{
    margin-left: 2px;
    border-radius: 2px;
    border: 2px none #191a18;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    display:flex;
    height: 25px;
    
}

.tab:active{

    height: 100px;
}




</style>