<template>
    <section>
        <div class="search-bar">
            <input type="text" placeholder="cerca movie" v-model="searchMovie">
            <button @click="$emit ('ricerca', searchMovie)">cerca</button>
        </div>
    </section>
</template>

<script>

export default {
        name: 'searchBar',
        data() {
            return {
                searchMovie: ''
            }
        },
        
    }
 
</script>

<style lang="scss" scoped>
</style>