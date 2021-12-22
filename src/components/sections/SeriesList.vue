
    <template>
    <div class="container">
        <h2>Serie TV</h2>
        <div class="card" v-for="(serie, index) in series" :key="index">
            <SerieCard :info='serie'/>
        </div>
             
    </div>
  
  
</template>

<script>
import SerieCard from "../commons/SerieCard.vue"
export default {
    name: 'SeriesList',
    props:{
        series: Array
    },
    components:{
        SerieCard
    }


}
</script>

<style>

</style>