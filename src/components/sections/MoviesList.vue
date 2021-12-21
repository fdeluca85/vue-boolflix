
    <template>
    <div class="container">
        <div class="card" v-for="(movie, index) in movies" :key="index">
            <MovieCard :info='movie'/>
        </div>
             
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