<template>
    <div class="album_card">
        <img :src="info.poster" :alt="info.author">

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
    padding: 16px;
    background-color: $main_color;
    height: 258px;
    
    img {
        max-width: 130px;
        margin: 0 auto;
    }

    .album_details {
        text-align: center;

        h3 {
        color: $titles_color;
        font-weight: 700;
        text-transform: $text_upercase;
        font-size: 15px;
        margin: 16px 0;
        }

        .album_text {
            color: $text_card;

            div:first-child {
                font-size: 13px;
            }

            div:last-child {
                font-size: 11px;
            }
        }
    }
}
</style>