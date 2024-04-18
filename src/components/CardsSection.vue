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
    <div class="container">
            <ul class="row cards-wrapper py-24">
                <li  class="col-3 p-6"
                v-for="(movie, i) in store.filteredMovies" :key="i"   
                >
                    <AppCard 
                    :title="movie.title"
                    :originalTitle="movie.original_title"
                    :originalLanguage="movie.original_language"
                    :voteAverage="movie.vote_average"
                    :backDrop="movie.backdrop_path"
                    :description="movie.overview"
                    />
                </li>
                <li  class="col-3 p-12"
                v-for="(tv, i) in store.filteredTv" :key="i"
                >
                    <AppCard 
                    :title="tv.name"
                    :originalTitle="tv.original_name"
                    :originalLanguage="tv.original_language"
                    :voteAverage="tv.vote_average"
                    :backDrop="tv.poster_path"
                    :description="tv.overview"
                    />
                </li>
            </ul>
    </div>
    
</template>

<style>

</style>