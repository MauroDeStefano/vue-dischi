<template>
  <main>
    <div v-if="toLoad" class="container p-5">
      <Albums 
      v-for="(album, index) in albums"
      :key="index"
      :album="album"
      
      />
    </div>
    <div v-else><Loader :titleLoader="'Stà Arrivando...'"/></div>
  </main>
</template>

<script>
import axios from 'axios';
import Albums from './Albums.vue';
import Loader from './Loader.vue';

export default {
  name: 'Main',
  components:{
    Albums,
    Loader
  },
  props:{
    stringToMain: String,
  },
  data(){
    return{
    
    albums: [],
      newUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      toLoad: false
    }
  },
  methods:{
    getApi(){
      axios.get(this.newUrl)
      .then(r => {
        this.albums = r.data.response;
        this.toLoad = true;
      })
      .catch( e => {
        console.log(e);
      })
    }
  },
  mounted(){
    this.getApi();
  }

}
</script>

<style lang="scss">

@import '~bootstrap/scss/bootstrap.scss';
@import '../assets/style/vars.scss';

main{
  background-color: $main-bg;
  min-height: 100vh;
}

</style>
