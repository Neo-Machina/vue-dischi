<template>
    <header>
        <div class="flex_img">
            <img src="../assets/img/logo_spotify.png" alt="spotify_logo">
        </div>
    </header>
</template>

<script>

export default {
    name: 'PageHeader',
    components: {

    }
}
</script>

<style lang="scss">
@import '../style/variables.scss';

header {
    height: 60px;
    background-color: $main_color;

    .flex_img {
        display: flex;
        height: 100%;
        align-items: center;

        img {
            width: 35px;
            margin-left: 20px;
        }
    }
}

</style>