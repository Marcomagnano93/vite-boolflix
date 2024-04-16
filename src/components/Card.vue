<script>
export default {
    props: {
       title: String,
       originalTitle: String,
       originalLanguage: String,
       voteAverage: Number,
       name: String,
       originalName: String,
    }

}

</script>

<template>
    <ol>
        <li v-if="name"><span>Titolo: </span>{{ name }}</li>
        <li v-if="originalName"><span>Titolo originale: </span>{{ originalName }}</li>
        <li v-if="title"><span>Titolo: </span>{{ title }}</li>
        <li v-if="originalTitle"><span>Titolo originale: </span>{{ originalTitle }}</li>
        <li><span>Lingua originale: </span><img :src="`../public/flags/${originalLanguage}.png`" alt=""></li>
        <li><span>Punteggio: </span>{{ voteAverage }}</li>
    </ol>

    
</template>

<style scoped>
/* debug */
span{
    color: red;
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