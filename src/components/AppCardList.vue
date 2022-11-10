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

</style>