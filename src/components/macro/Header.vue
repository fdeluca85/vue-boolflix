<template>
    <header>
        <SearchBar @ricerca="passValue" />
    </header>
</template>

<script>
import SearchBar from '../commons/SearchBar.vue';
export default {
    name: 'Header',
    components: {
        SearchBar
    },
    methods: {
        passValue(valore){
            this.$emit('ricerca', valore)

        }
    }
}
</script>

<style lang="scss" scoped>

</style>