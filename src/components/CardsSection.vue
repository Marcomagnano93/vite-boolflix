<script>
import {store} from '../store.js';
import AppCard from './AppCard.vue'

export default{

data() {
  return {
      store: store,

      }
    },
components: {
    AppCard,

    }
}
</script>

<template>
    <h3>i film:</h3>
    <ul>
        <li
        v-for="(movie, i) in store.filteredMovies" :key="i"
        >
            <AppCard 
            :title="movie.title"
            :originalTitle="movie.original_title"
            :originalLanguage="movie.original_language"
            :voteAverage="movie.vote_average"

            />
        </li>
        <li
        v-for="(tv, i) in store.filteredTv" :key="i"
        >
            <AppCard 
            :title="tv.name"
            :originalTitle="tv.original_name"
            :originalLanguage="tv.original_language"
            :voteAverage="tv.vote_average"

            />
        </li>
    </ul>
</template>

<style>

</style>