<template>
    <section>
        <div class="search-bar">
            <input type="text" placeholder="Titolo..." v-model="searchMovie">
            <button @click="cercaResetta()">cerca</button>
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
        methods: {
            cercaResetta() {
                this.$emit ('ricerca', this.searchMovie,);
                this.searchMovie = "";                
            }
} 
    }
 
</script>

<style lang="scss" scoped>
button{
    padding: 10px 15px;
    text-transform: uppercase;
    margin: 0 10px;
    border-radius: 5px;
    border: none;
    cursor: pointer;
}
input{
    padding: 10px 15px;
    border-radius: 5px;
    border: none;
}

</style>