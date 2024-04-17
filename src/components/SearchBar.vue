<script>
import axios from 'axios';
import {store} from '../store.js';


export default{

data() {
  return {
      userSearch: '',

  }
},
methods: {
  fetchData(search){
    axios.get(`https://api.themoviedb.org/3/search/movie?api_key=48511f7dd11f8a5f8b87b3ac0839794f&query=${search}`).then((res) => {
 
      store.filteredMovies = res.data.results
    
    })
    axios.get(`https://api.themoviedb.org/3/search/tv?api_key=48511f7dd11f8a5f8b87b3ac0839794f&query=${search}`).then((restv) => {

      store.filteredTv = restv.data.results
    })  
  }
}
}
</script>

<template>

    <input type="text" v-model="userSearch" @keyup.enter="fetchData(userSearch)">
    
    <button @click="fetchData(userSearch)"
    >
        Cerca
    </button>


</template>

<style>

</style>