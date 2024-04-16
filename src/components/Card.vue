<script>
export default {
    props: {
       title: String,
       originalTitle: String,
       originalLanguage: String,
       voteAverage: Number
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

<style>
span{
    color: red;
}
img{
    max-width: 18px;
    object-fit: cover;
}
</style>