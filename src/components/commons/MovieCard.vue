<template>
    <div class="movie_card">
        <ul>
            <li>{{info.title}}</li>
            <li>{{info.original_title}}</li>
            <li>{{info.vote_average}}</li>
        </ul>
        
    </div>
  
</template>

<script>
export default {
    name: 'MovieCard',
    props: {
        info: Object
    }
}
</script>

<style>

</style>