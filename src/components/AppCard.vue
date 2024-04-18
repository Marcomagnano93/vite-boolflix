<script>
export default {
    props: {
       title: String,
       originalTitle: String,
       originalLanguage: String,
       voteAverage: Number,
       backDrop: String,
       description: String
    },
    data() {
  return {
      stars: this.mathRound(this.voteAverage),
      emptyStars: this.restStarCalculator(this.voteAverage),

      }
    },
    methods: {
        mathRound(n){
            let nd2 = n / 2;
            let roundedN = Math.round(nd2);
            return roundedN
        },
        restStarCalculator(n){
            const rest = 5 - this.mathRound(n);
            return rest
        }
    }

}

</script>

<template>
    
    <div class="card">
        <div class="poster">
            <img :src="`https://image.tmdb.org/t/p/w342${backDrop}`" alt="" >
        </div>

        <div class="card-body">
            <div class="title"><span>Titolo: </span> <h4>{{ title }}</h4></div>
            <div class="original-title"><span>Titolo originale: </span> <h4>{{ originalTitle }}</h4></div>
            <div class="description"><span>Trama: </span><p>{{ description }}</p></div>
            <div class="language"><span>Lingua originale: </span><img :src="`../public/flags/${originalLanguage}.png`" alt="" class="flags"></div>
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