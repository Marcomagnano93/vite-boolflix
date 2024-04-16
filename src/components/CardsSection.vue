<script>
import {store} from '../store.js';
import Card from './Card.vue'

export default{

data() {
  return {
      store: store,

      }
    },
components: {
    Card,

    }
}
</script>

<template>
    <h3>i film:</h3>
    <ul>
        <li
        v-for="(movie, i) in store.filteredMovies"
        >
            <card 
            :title="movie.title"
            :originalTitle="movie.original_title"
            :originalLanguage="movie.original_language"
            :voteAverage="movie.vote_average"
            />
        </li>
    </ul>
</template>

<style>

</style>