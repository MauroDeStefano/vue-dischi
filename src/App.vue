<template>
  <Header @selectedType="selectedHeader"/>
  <Main :stringToMain="headerToMain"/>
  <Footer />

</template>

<script>

import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';


export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  },
  
  data(){
    return{
    headerToMain: "",
    }
  },
  methods:{
    selectedHeader(text){
      this.headerToMain = text;
      console.log("questa è l'app", this.headerToMain);
    }
  },
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';

</style>
