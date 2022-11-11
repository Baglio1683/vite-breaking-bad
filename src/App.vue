<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue"
import AppCardList from "./components/AppCardList.vue"
import AppSingleCard from "./components/AppSingleCard.vue"
import AppLoad from "./components/AppLoad.vue"
import { store } from "./store";



export default{

components: {
  AppHeader,
  AppCardList, 
  AppSingleCard, 
  AppLoad
},

data(){

  return{
    store,
  }
}, 

methods: {
  searchActors(numberOfActor){

    if(numberOfActor == 2){
      this.store.loading = true;
      axios.get("https://www.breakingbadapi.com/api/characters?category=Better+Call+Saul").then((resp) => {
      this.store.characters = resp.data;
      this.store.loading = false;
      });
    }

    if(numberOfActor == 1){
      this.store.loading = true;
      axios.get("https://www.breakingbadapi.com/api/characters?category=Breaking+Bad").then((resp) => {
      this.store.characters = resp.data;
      this.store.loading = false;
    
    }); 
     }
    
    if(numberOfActor ==3){

      this.store.loading = true;
      axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
      this.store.loading = false;
    
    }); 

    }
  }

}

}


</script>

<template>

<body>
  <AppHeader @search="searchActors" />
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