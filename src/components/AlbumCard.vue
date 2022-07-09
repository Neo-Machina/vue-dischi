<template>
    <div class="album_card text-center">
        <div class="d-inline-block">
            <img :src="info.poster" :alt="info.author">
        </div>

        <div class="album_details">
            <h3> {{ info.title }} </h3>

            <div class="album_text">
                <div> {{ info.author }} </div>

                <div> {{ info.year }} </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'AlbumCard',
    props: ['info']
}
</script>

<style lang="scss">
@import '../style/variables.scss';

.album_card {
    padding: 10px;
    background-color: $main_color;
    
    img {
        width: 120px;
    }
    .album_details {
        h3 {
        color: $titles_color;
        font-weight: 700;
        text-transform: $text_upercase;
        font-size: 17px;
        }

        .album_text {
            color: $text_card;
        }
    }
}
</style>