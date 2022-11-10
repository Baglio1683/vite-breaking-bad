<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue"
import AppCardList from "./components/AppCardList.vue"
import AppSingleCard from "./components/AppSingleCard.vue"
import { store } from "./store";



export default{

components: {
  AppHeader,
  AppCardList, 
  AppSingleCard
},

data(){

  return{
    store,
  }
}, 

created(){
   
     // loading setting true
      this.store.loading = true;
      axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data.results;
      this.store.loading = false;

    });


}, 

}

</script>

<template>

<body>
  <AppHeader /> 
  <AppCardList /> 
</body>

</template>

<style lang="scss">
@use "./styles/general.scss" as*;
@use "./styles/partials/variables" as*; 

body{
  background-color: $body_color;
}


</style>