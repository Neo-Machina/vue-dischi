<template>
    <section>
        <div class="container">
            <SelectComponent />

            <div v-if="loading" class="row">
                <div class="col" v-for="(element,index) in albumsArray" :key="index">
                    <AlbumCard :info="element" />
                </div>
            </div>

            <LoaderComponent v-else />
        </div>
    </section>
</template>

<script>
import axios from "axios";

import AlbumCard from './AlbumCard.vue';
import LoaderComponent from './LoaderComponent.vue';
import SelectComponent from './SelectComponent.vue';


export default {
    name: 'AlbumList',
    components: {
        AlbumCard,
        LoaderComponent,
        SelectComponent
    },
    data() {
        return {
            url:'https://flynn.boolean.careers/exercises/api/array/music',
            albumsArray: [],
            loading: false,
            isLoaded: null
        }
    },
    methods: {
        getAlbums() {
            axios.get(this.url).then((response) => {
                this.albumsArray = response.data.response;
                this.loading = true; 
            })
            .catch((err) => {
                console.log('Error', err);
            });
        },

        loadingAlbumList() {
            setTimeout(() => this.getAlbums(), 1000); 
        }
    },
    created() {
        this.loadingAlbumList();
    },
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