<script>
export default {
    props: {
       title: String,
       originalTitle: String,
       originalLanguage: String,
       voteAverage: Number,
    }

}

</script>

<template>
    <ol>
        <li><span>Titolo: </span>{{ title }}</li>
        <li><span>Titolo originale: </span>{{ originalTitle }}</li>
        <li><span>Lingua originale: </span><img :src="`../public/flags/${originalLanguage}.png`" alt=""></li>
        <li><span>Punteggio: </span>{{ voteAverage }}</li>
    </ol>

    
</template>

<style scoped>
/* debug */
span{
    color: blue;
}
img{
    max-width: 18px;
    object-fit: cover;
}
ol{
    margin-bottom: 20px;
    border-bottom: 2px solid black;
}
</style>