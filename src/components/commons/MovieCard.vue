<template>
    <div class="movie_card">
        <ul>
            <li>{{info.title}}</li>
            <li>{{info.original_title}}</li>
            <li><span>Voti: </span>
                <div class="star" v-for="index in starVote(info.vote_average)" :key="index"><i class="fas fa-star"></i></div>
            </li>
            <li>Lingua originale: {{lingua()}}</li>
        </ul>
        
    </div>
  
</template>

<script>
export default {
    name: 'MovieCard',
    props: {
        info: Object
    },
    methods:{
        lingua(){
            if (this.info.original_language == 'it') {
                    return '\uD83C\uDDEE\uD83C\uDDF9'
                } else if (this.info.original_language == 'us') {
                    return '\uD83C\uDDFA\uD83C\uDDF8'
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
        starVote (voto){
                return voto = Math.ceil(voto / 2)
                
            }
    }
}
</script>

<style>

</style>