<template>
  <div id="app">
    <HeaderComponent />
    <MainComponent />
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
  components: {
    HeaderComponent,
    MainComponent
}
}
</script>

<style lang="scss">
    @import url('./style/index.scss');
</style>
