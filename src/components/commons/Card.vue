<template>
    <div class="card">
        <div class="poster">
            <img v-if="info.poster_path == null" src="../../assets/img/notfound.png" alt="">
            <img v-else :src="'https://image.tmdb.org/t/p/w342/' + info.poster_path"
                :alt="info.title"> 
        </div> 
        <div class="info">
            <h2>{{info.title ? info.title :info.name}}</h2>
            <h3 v-if="mostraTitolo()">{{info.original_title ? info.original_title :info.original_name }}</h3>
            <h3>Lingua originale: {{lingua()}}</h3> 
            <div class="star">
                <i v-for="index in starVote(info.vote_average)" :key="index" class="fas fa-star"></i>
                <i v-for="i in (5 - starVote(info.vote_average))" :key="'vuote'+i" class="far fa-star"></i>
            </div>
        </div>      
    </div>
  
</template>

<script>
export default {
    name: 'Card',
    props: {
        info: Object
    },
    methods:{
        lingua(){
            if (this.info.original_language == 'it') {
                    return '\uD83C\uDDEE\uD83C\uDDF9'
                } else if (this.info.original_language == 'us') {
                    return '\ud83c\uddec\ud83c\udde7'
                } else if (this.info.original_language == 'en') {
                    return '\ud83c\uddec\ud83c\udde7'
                } else if (this.info.original_language == 'fr') {
                    return '\uD83C\uDDE8\uD83C\uDDF5'
                } else if (this.info.original_language == 'es') {
                    return '\uD83C\uDDEA\uD83C\uDDF8'
                } else if (this.info.original_language == 'ja') {
                    return '\uD83C\uDDEF\uD83C\uDDF5'
                } else {
                    return this.info.original_language
                }
        },
        starVote (vote){
                return vote = Math.ceil(vote / 2)
                
            },
        mostraTitolo (){
            if (this.info.original_title != this.info.title || this.info.original_name != this.info.name){
                return true
            } 
            return false

        }
    }
}
</script>

<style lang="scss" scoped>

.star{
    display: inline;
    color: gold;
}
.card{
    padding: 10px;
    position: relative;  
    :hover .info{
        opacity: 1;
    }

}
.poster:hover{
    filter: brightness(0.3);
}
.info{
    position: absolute;
    bottom: 50px;
    left:20px;     
    transition: .5s ease;
    opacity:0;  
}
</style>