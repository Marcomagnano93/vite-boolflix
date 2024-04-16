<script>
import SearchBar from './components/SearchBar.vue';
import CardsSection from './components/CardsSection.vue';
import {store} from './store.js'

export default{

  components: {
    SearchBar,
    CardsSection,

  }
}


</script>

<template>
  <div class="container">

    <div class="red">
      <h1>Cerca un film</h1>
    </div>

    <SearchBar/>

    <CardsSection/>
    
  </div>


</template>

<style>

</style>
