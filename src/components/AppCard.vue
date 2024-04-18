<script>
import axios from 'axios';

export default {
    props: {
       title: String,
       originalTitle: String,
       originalLanguage: String,
       voteAverage: Number,
       backDrop: String,
       description: String,
       idNumber: Number
    },
    data() {
  return {
      stars: this.mathRound(this.voteAverage),
      emptyStars: this.restStarCalculator(this.voteAverage),
      actorsArray: [],
      genresArray: []

      }
    },
    methods: {
        mathRound(n){
            let nd2 = n / 2;
            let roundedN = Math.ceil(nd2);
            return roundedN
        },
        restStarCalculator(n){
            const rest = 5 - this.mathRound(n);
            return rest
        },
        alternativeFlag(lang){
            if(lang !== 'it' && lang !== 'en' && lang !== 'es' && lang !== 'fr' && lang !== 'pt'){
                return lang
            }
            else{ return ''}
        },
        fetchActors(movieId){
            axios.get(`https://api.themoviedb.org/3/movie/${movieId}/credits?api_key=48511f7dd11f8a5f8b87b3ac0839794f`).then((res) => {
        
            this.actorsArray = res.data.cast.slice(0, 4);
            
            })
        },
        fetchGenre(movieId){
            axios.get(`https://api.themoviedb.org/3/movie/${movieId}?api_key=48511f7dd11f8a5f8b87b3ac0839794f`).then((res) => {
        
            this.genresArray = res.data.genres;
            
            })
    }
}
}

</script>

<template>
        <!-- card poster -->
    <div class="card" @mouseover="fetchActors(idNumber)">
        <div class="poster">
            <img :src="`https://image.tmdb.org/t/p/w500${backDrop}`" alt="" >
        </div>
        <!-- card movie/tv title and info -->
        <div class="card-body" :class="backDrop === null ? 'no-img' : ''">
            <div class="title"><span>Titolo: </span> <h4>{{ title }}</h4></div>
            <div class="original-title"><span>Titolo originale: </span> <h4>{{ originalTitle }}</h4></div>
            <div class="description"><span>Trama: </span><p>{{ description }}</p></div>
        <!-- card movie /tv actors -->
            <div> <span>Attori: </span>
                <ul class="actors" >
                    <li v-for="(actor, i) in actorsArray" :key="i">
                        {{ actor.name }}
                    </li>
                </ul>
            </div>
        <!-- card lang & stars -->
            <div class="language"><span>Lingua originale: </span> <span> {{ alternativeFlag(originalLanguage) }} </span>
                <img :src="`../public/flags/${originalLanguage}.png`" alt="" class="flags">
            </div>

            <div class="stars">
                <font-awesome-icon icon="fa-solid fa-star"
                v-for="(star, i) in stars" :key="i"/>

                <font-awesome-icon icon="fa-regular fa-star"
                v-for="(emptyStar, i) in emptyStars" :key="i" />       
            </div>

        </div>
    </div>
</template>

<style>

</style>