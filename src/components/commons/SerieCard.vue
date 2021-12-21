<template>
    <div class="serie_card">
        <ul>
            <li>{{info.name}}</li>
            <li>{{info.original_name}}</li>
            <li>{{info.vote_average}}</li>
        </ul>
        
    </div>
  
</template>

<script>
export default {
    name: 'SerieCard',
    props: {
        info: Object
    }
}
</script>

<style>

</style>