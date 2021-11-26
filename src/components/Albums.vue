<template>
  <div class="album-box text-center">
    <div>
      <img class="image" :src="album.poster" :alt="album.title">
      <h4>{{album.title}}</h4>
      <span>{{album.genre}}</span>
      <span>{{album.year}}</span>
    </div>
    
  </div>
</template>

<script>
  export default{
    name: "Albums",
    props:{
      album: Object
    }
  }
</script>

<style lang="scss" scoped>
@import '~bootstrap/scss/bootstrap.scss';
@import '../assets/style/vars.scss';

  .album-box {
    float: left;
    width: 180px;
    height: 350px;
    padding: 15px;
    margin: 20px;
    background-color: $primary-bg;

    .image{
      width: 100%;
    }

    h4{
      color: white;
      margin: 5px 0;
    }

    span{
      display: block;
      color: lightgray;
    }
  }
  

</style>