<template>
  <main>
    <div class="container p-5">
      <Albums 
      v-for="(album, index) in albums"
      :key="index"
      :album="album"
      />
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import Albums from './Albums.vue';

export default {
  name: 'Main',
  components:{
    Albums,
  },
  data(){
    return{
      albums: [],
      newUrl: "https://flynn.boolean.careers/exercises/api/array/music",
    }
  },
  methods:{
    getApi(){
      axios.get(this.newUrl)
      .then(r => {
        this.albums = r.data.response;
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
  height: 100vh;
}

</style>
