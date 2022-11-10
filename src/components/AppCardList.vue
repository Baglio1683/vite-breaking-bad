<script>
import AppSingleCard from './AppSingleCard.vue';
import { store } from "../store";

export default{
    name: "AppCardList",

    components: {
        AppSingleCard
    },

data(){
    return{
      store
    }
}

}
</script>

<template>

    <div class="container">
      
          <div class="col_5" v-for="character in store.characters">
            <AppSingleCard :character="character"/>
          </div>  
    </div>


</template>

<style lang="scss" scoped> 
    
    .col_5{
      font-size: small;
      background-color:  #2E3A46;
      color: white;
      text-align: center;
      padding-top: 10px;
      padding-bottom: 10px;
    }

  

</style>