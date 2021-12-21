<template>
    <main>
        <MoviesList :movies="movies"/>
    </main>
</template>

<script>
import MoviesList from "../sections/MoviesList.vue"
export default {
    name: 'Main',
    components: {
        MoviesList,
    },
    props:{
        movies: Array
    }
}
</script>

<style lang="scss" scoped>
</style>