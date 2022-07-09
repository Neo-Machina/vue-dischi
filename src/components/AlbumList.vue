<template>
    <section>
        <div class="container">
            <div class="row row-cols-5">
                <div class="col" v-for="(element,index) in albumsArray" :key="index">
                    <AlbumCard :info="element" />
                </div>
            </div>
        </div>
    </section>
</template>

<script>

import axios from "axios";

import AlbumCard from './AlbumCard.vue';

export default {
    name: 'AlbumList',
    components: {
        AlbumCard
    },
    data() {
        return {
            url:'https://flynn.boolean.careers/exercises/api/array/music',
            albumsArray: []
        }
    },
    created() {
        this.getAlbums();
    },
    methods: {
        getAlbums() {
            axios.get(this.url).then((response) => {
                this.albumsArray = response.data.response;
            })
            .catch((err) => {
                console.log('Error', err);
            });
        }
    }
}
</script>

<style lang="scss">
@import '../style/variables.scss';

section {
    background-color: #1e2d3b;
    height: calc(100vh - 60px);
}
</style>