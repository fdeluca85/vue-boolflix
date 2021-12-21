<template>
    <div class="container">
        <MovieCard />        
    </div>
  
</template>

<script>
import MovieCard from "../commons/MovieCard.vue"
export default {
    name: 'MoviesList',
    props:{
        movies: Array
    },
    components:{
        MovieCard
    }


}
</script>

<style>

</style>