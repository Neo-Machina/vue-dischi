<template>
    <div>
        <select name="" id="">
            <option v-for="(genre, index) in genreArray" :key="index" :value="genre">{{ genre }}</option>
        </select>
    </div>
</template>

<script>
export default {
    name:'SelectGenre',
    props: {
        genreMusic: String,
        genreArray: []
    }
}
</script>

<style lang="scss" scoped>

</style>