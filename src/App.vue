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
  <header>
    <SearchBar/>
  </header>

  <main>
    <CardsSection/>
  </main>

    
    
</template>

<style>
main {
  width: 100%;
  min-height: 100vh;
  background-color: rgb(34, 40, 47);
}
</style>
