<template>
  <main>
    <div v-if="toLoad" class="container p-5">
      <Albums 
      v-for="(album, index) in filterAlbum"
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
        console.log("questa è main",this.stringToMain);
      })
      .catch( e => {
        console.log(e);
      })
    },
   
  },
  mounted(){
    this.getApi();
    
  },
  computed:{
    filterAlbum(){
      if (this.stringToMain === "" || this.stringToMain === "All"){
        return this.albums;
      }else{
        let albumsFiltered =[];
        for(let i = 0; i < this.albums.length -1 ; i++){
          if (this.albums[i].genre.toUpperCase().includes(this.stringToMain.toUpperCase())){
          albumsFiltered.push(this.albums[i]);
          }
        }
        return albumsFiltered;
      }
    }
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
