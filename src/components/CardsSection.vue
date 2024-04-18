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
        <div v-if="store.filteredMovies.length === 0 && store.filteredTv.length === 0" class="intro">
            <h1>Benvenuto!</h1>
            <p>Cerca un film nel catalogo...</p>
        </div>
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
                    :idNumber="movie.id"
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
                    :idNumber="tv.id"
                    />
                </li>
            </ul>
    </div>
    
</template>

<style scoped>
.intro{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 20px;
    padding: 50px;
    color: white;
}

.intro p {
    font-size: 32px;
}

.intro h1{
    font-size: 50px;
}
</style>