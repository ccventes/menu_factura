<script  lang="ts">
import ImageSelectorVue from './components/ImageSelector.vue';
import TabBillinfo from './components/TabBillinfo.vue';
export default {
  name: 'App',
  components: {ImageSelectorVue,TabBillinfo},


}
</script>

<template>
 
<div class = "container">
  <ImageSelectorVue />
  <TabBillinfo />

</div>
</template>

<style scoped>

.container{
  display:flex;
  justify-content: left;
  flex-direction: row;

}
.TabBillinfo{
  border: dashed red;  

}

</style>
