<template>
        <section>
            <h2>Serie TV</h2>
            <div class="container">
                <div class="card" v-for="(serie, index) in series" :key="index">
                    <Card :info='serie'/>
                </div>             
            </div>
        </section> 
</template>

<script>
import Card from "../commons/Card.vue"
export default {
    name: 'SeriesList',
    props:{
        series: Array
    },
    components:{
        Card
    }


}
</script>

<style lang="scss" scoped>
.card{
    
    display: flex;


}



</style>