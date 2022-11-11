<script>
import { store } from "../store";

export default {
    name: "AppHeader",

    data(){
      return{
        store,
        selected : "", 
      }
    }, 
}

</script>

<template>

    <header>
       <h1>Breaking Bad Api</h1>
    </header>

    <div class="container">

      <select v-model="selected">
        <option disabled value="">Select category</option>
        <option value="1">Breaking Bad</option>
        <option value="2">Better Call Saul</option>
        <option value="3">All categories</option>
      </select>
      <button @click="$emit('search',selected)">Start</button>
      <p>Il numero degli attori è : {{store.characters.length}} </p>
    </div>

</template>

<style lang="scss" scoped>
h1{
   color: white; 
   padding: 1rem;
   margin-bottom: 2rem;
}
</style>