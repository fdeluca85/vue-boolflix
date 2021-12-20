<template>
    <section>
        <div class="search-bar">
            <input type="text" placeholder="cerca movie" v-model="searchMovie">
            <button @click="ricerca">cerca</button>
        </div>
    </section>
</template>

<script>
import axios from 'axios'
export default {
        name: 'searchBar',
        data() {
            return {
                movie: [],
                searchMovie: ''
            }
        },
        methods: {
            ricerca() {
                axios.get('https://api.themoviedb.org/3/search/movie', {
                        params: {
                            api_key: 'd709e60f4da8bcd79a37874605d0272c',
                            query: this.searchMovie,
                            language: 'it-IT'
                        }
                    })
                    .then((response) => {
                        console.log(response.data.results);
                        this.movie = response.data.results
                        console.log(this.movie);
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