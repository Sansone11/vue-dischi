<template>
  <div>
    <MainHeader @musicGenre="onSearch" />
    <MainContent :options="searchProp" />
  </div>
</template>

<script>
import MainHeader from './components/MainHeader.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',

  data(){
    return{
      searchProp:'',
    }
  },
  components: {
    MainHeader,
    MainContent,

  },
  methods: {
    onSearch(data){
      this.searchProp = data
    }
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
