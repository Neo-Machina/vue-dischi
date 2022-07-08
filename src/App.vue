<template>
  <div id="app">
    <PageHeader />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import PageHeader from './components/PageHeader.vue'

export default {
  name: 'App',
  components: {
    PageHeader

  }
}
</script>

<style lang="scss">
@import './style/common.scss'
</style>
