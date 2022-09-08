<template>
  <div id="app">
    <HeaderComponent @searchGen="searchGen" @searchAut="searchAut"  />
    <MainComponent :genre="searchGenre" :author="searchAuthor" />
  </div>
</template>

<script>
  // Normal import
// import HeaderComponent from './components/HeaderComponent.vue';
// import MainComponent from './components/MainComponent.vue';

// Bonus import 
import HeaderComponent from './bonus/components/HeaderComponent.vue';
import MainComponent from './bonus/components/MainComponent.vue';

export default {
  name: 'App',
  data() {
    return {
      searchGenre: '',
      searchAuthor: ''
    }
  },
  components: {
    HeaderComponent,
    MainComponent
  },
  methods: {
    searchGen(data) {
      // console.log(data)
      this.searchGenre = data
      return this.searchGenre
    },
    searchAut(data) {
      // console.log(data)
      this.searchAuthor = data
      return this.searchAuthor
    }
  }
}
</script>

<style lang="scss">
@import url('./style/index.scss');
</style>
