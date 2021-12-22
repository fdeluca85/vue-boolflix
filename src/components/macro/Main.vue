<template>
    <main>
        <MoviesList :movies="movies"/>
        <SeriesList :series="series"/>
    </main>
</template>

<script>
import MoviesList from "../sections/MoviesList.vue"
import SeriesList from "../sections/SeriesList.vue"
export default {
    name: 'Main',
    components: {
        MoviesList,
        SeriesList
    },
    props:{
        movies: Array,
        series: Array
    }
}
</script>

<style lang="scss" scoped>
main{
    padding: 20px;
}
</style>