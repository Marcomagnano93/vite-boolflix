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
        <li><span>Lingua originale: </span>{{ originalLanguage }}</li>
        <li><span>Punteggio: </span>{{ voteAverage }}</li>
    </ol>
</template>

<style>
span{
    color: red;
}
</style>