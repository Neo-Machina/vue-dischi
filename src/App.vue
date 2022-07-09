<template>
  <div id="app">
    <PageHeader />

    <main>
      <AlbumList />
    </main>
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue';
import AlbumList from './components/AlbumList.vue';

export default {
  name: 'App',
  components: {
    PageHeader,
    AlbumList
  }
}
</script>

<style lang="scss">
@import './style/common.scss'
</style>
