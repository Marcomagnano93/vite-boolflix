<script>
export default {
    props: {
       title: String,
       originalTitle: String,
       originalLanguage: String,
       voteAverage: Number,
       backDrop: String
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
    <ol>
        <li><span>Titolo: </span>{{ title }}</li>
        <li><span>Titolo originale: </span>{{ originalTitle }}</li>
        <li><span>Lingua originale: </span><img :src="`../public/flags/${originalLanguage}.png`" alt="" class="flags"></li>
        <li><span>Punteggio: </span>{{ mathRound(voteAverage) }}</li>
        <li>
            <font-awesome-icon icon="fa-solid fa-star"
            v-for="(star, i) in stars" :key="i"/>
            <font-awesome-icon icon="fa-regular fa-star"
            v-for="(emptyStar, i) in emptyStars" :key="i" />
        </li>
        <li><img :src="`https://image.tmdb.org/t/p/w342${backDrop}`" alt=""></li>
    </ol>

    
</template>

<style scoped>
/* debug */
span{
    color: blue;
}

.flags {
    max-width: 18px;
}

ol{
    margin-bottom: 20px;
    border-bottom: 2px solid black;
}
img {
    width: 80px;
    object-fit: cover;
}
</style>