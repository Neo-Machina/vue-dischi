<template>
        <select @change="changeGenre($event)" name="" id="">
            <option value="">Tutti i generi degli album</option>
            <option v-for="(genre, index) in genreArray" :key="index" :value="genre">{{ genre }}</option>
        </select>
</template>

<script>
export default {
    name:'SelectGenre',
    props: {
        genreArray: [],
        genreMusic: String
    },
    methods: {
        changeGenre($event) {
            this.$emit('updateGenre', $event.target.value);
        }
    }
}
</script>

<style lang="scss" scoped>
select {
    margin: 20px 0;
}
</style>