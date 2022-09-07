<template>
  <MainHeader />
  <MainContent />
</template>

<script>
import MainHeader from './MainHeader.vue';
import MainContent from './MainContent.vue';

export default {
  name: 'App',
  components: {
    MainHeader,
    MainContent,
   
}
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
