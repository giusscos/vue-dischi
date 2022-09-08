<template>
  <div id="app">
    <!-- Normail -->
    <HeaderComponent @searchGen="searchGenre" />
    <MainComponent :genre="currentGenre" />

    <!-- Bonus -->
    <!-- <BonusHeaderComponent @searchGen="searchGenre" @searchAut="searchAuthor"  />
    <BonusMainComponent :genre="currentGenre" :author="currentAuthor" /> -->
  </div>
</template>

<script>
// Normal import
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';

// Bonus import 
// import BonusHeaderComponent from './bonus/components/BonusHeaderComponent.vue';
// import BonusMainComponent from './bonus/components/BonusMainComponent.vue';

export default {
  name: 'App',
  data() {
    return {
      currentGenre: '',
      // Bonus
      // currentAuthor: ''
    }
  },
  components: {
    HeaderComponent,
    MainComponent
    // Bomus
    // BonusHeaderComponent,
    // BonusMainComponent
  },
  methods: {
    searchGenre(data) {
      // console.log(data)
      this.currentGenre = data
      return this.currentGenre
    },
    // Bonus
    // searchAuthor(data) {
    //   // console.log(data)
    //   this.currentAuthor = data
    //   return this.currentAuthor
    // }
  }
}
</script>

<style lang="scss">
@import url('./style/index.scss');
</style>
