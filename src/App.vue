<template>
  <div id="app">
    <HeaderComponent @search="searchAlbum" />
    <MainComponent :genre="searchGenre" />
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
// Normal import
import MainComponent from './components/MainComponent.vue';

// Bonus import 
// import MainComponent from './bonus/components/MainComponent.vue';

export default {
  name: 'App',
  data() {
    return {
      searchGenre: ''
    }
  },
  components: {
    HeaderComponent,
    MainComponent
  },
  methods: {
    searchAlbum(data) {
      // console.log(data)
      this.searchGenre = data
      return this.searchGenre
    }
  }
}
</script>

<style lang="scss">
@import url('./style/index.scss');
</style>
