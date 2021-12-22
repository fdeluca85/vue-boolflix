<template>
    <header>
        <img src="../../assets/img/logo.png" alt="boolflix logo">
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
header{
    background-color: black;
    height: 80px;
    display: flex;
    justify-content: space-between;
    line-height: 80px;
    padding: 5px;
    }

</style>