<template>
        <select @change="changeArtist($event)" name="">
            <option value="">Tutti gli artisti</option>
            <option v-for="(artist, index) in artistsArray" :key="index" :value="artist">{{ artist }}</option>
        </select>
</template>

<script>
export default {
    name:'SelectArtist',
    props: {
        artistsArray: [],
        artistMusic: String
    },
    methods: {
        changeArtist($event) {
            this.$emit('updateArtist', $event.target.value);
        }
    }
}
</script>

<style lang="scss" scoped>
</style>