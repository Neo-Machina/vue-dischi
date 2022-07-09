<template>
    <section>
        <div class="container">
            <div class="row">
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
    height: calc(100vh - 50px);

    .container {
        height: 100%;
        display: flex;
        align-items: center;
        
        .row {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;

            .col {
                margin: 8px 0;
                width: calc((100% / 5) - 23px);
            }
        }
    }
}
</style>