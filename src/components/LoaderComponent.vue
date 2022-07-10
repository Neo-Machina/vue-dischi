<template>
    <div class="loader">
        <h3 class="loading-message">LOADING ...</h3>
    </div>
</template>

<script>


export default {
  name: 'LoaderComponent',
  components: {
  }
}
</script>

<style lang="scss">
.loader {
    position: fixed;
    width: 100%;
    height: 100%;
    background: #fff;
    z-index: 100;
    top: 0;
    left: 0;
    background-repeat: no-repeat;
    background-position: center center;
    background-color: #f1f2f3;
    background-image: url('../assets/img/Bean Eater-1s-200px.gif');

    .loading-message {
        position: fixed;
        width: 100%;
        text-align: center;
        top: calc( 50% + 70px);
    }
}
</style>