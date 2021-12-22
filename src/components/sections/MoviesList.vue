
    <template>
    <div class="container">
        <h2>Film</h2>
        <div class="card" v-for="(movie, index) in movies" :key="index">
            <Card :info='movie'/>
        </div>
             
    </div>
  
  
</template>

<script>
import Card from "../commons/Card.vue"
export default {
    name: 'MoviesList',
    props:{
        movies: Array
    },
    components:{
        Card
    }


}
</script>

<style lang="scss" scoped>

</style>