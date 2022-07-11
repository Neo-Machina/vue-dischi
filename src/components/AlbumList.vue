<template>
    <section>
        <div class="container">
            <SelectGenre :genreMusic="selectedGenre" :genreArray="genreArray" @updateGenre="changeValueGenre($event)"/>

            <div v-if="loading" class="row">
                <div class="col" v-for="(element,index) in filteredGenre" :key="index">
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
import SelectGenre from './SelectGenre.vue';


export default {
    name: 'AlbumList',
    components: {
        AlbumCard,
        LoaderComponent,
        SelectGenre
    },
    data() {
        return {
            url:'https://flynn.boolean.careers/exercises/api/array/music',
            albumsArray: [],
            loading: false,
            isLoaded: null,
            genreArray: [
                'Rock',
                'Pop',
                'Metal',
                'Jazz'
            ],
            selectedGenre: ''
        }
    },
    computed: {
        filteredGenre() {
            if(this.selectedGenre === '') {
                return this.albumsArray;
            }
            else {
                return this.albumsArray.filter(album => album.genre === this.selectedGenre);
            }
        }
    },
    methods: {
        getAlbums() {
            axios.get(this.url).then((response) => {
                this.albumsArray = response.data.response;
            })
            .catch((err) => {
                console.log('Error', err);
            });
        },

        loadingAlbumList() {
            setTimeout(() => this.loading = true, 1000); 
        },
        changeValueGenre(newValue) {
            this.selectedGenre = newValue;
        }
    },
    created() {
        this.getAlbums();
        this.loadingAlbumList();
    }
}
</script>

<style lang="scss">
@import '../style/variables.scss';

section {
    background-color: #1e2d3b;
    height: calc(100vh - 50px);

    .container {        
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