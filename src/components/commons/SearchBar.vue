<template>
    <section>
        <div class="search-bar">
            <input type="text" placeholder="cerca film">
            <button @click="ricerca">cerca</button>
        </div>
    </section>
</template>

<script>
import axios from 'axios'
export default {
        name: 'searchBar',
        
        methods: {
            ricerca() {
                axios.get('https://api.themoviedb.org/3/search/movie', {
                        params: {
                            api_key: 'd709e60f4da8bcd79a37874605d0272c',
                            query: '',
                            language: 'it-IT'
                        }
                    })                    
                    .then(function (response) {
                        console.log(response);
                    })
                    .catch(function (error) {
                        console.log(error);
                    })
            }
        }
    }
 
</script>

<style lang="scss" scoped>
</style>