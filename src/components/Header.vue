<template>
  <div class="d-flex align-content-center align-middle">
    <img  src="https://cdn.discordapp.com/attachments/887685956050780201/913759060090843156/spotify-logo.png" alt="Logo">
  </div>
</template>

<script>
export default {
  name: 'Header',
  props:{
    
  }
}
</script>

<style lang="scss" scoped>

@import '~bootstrap/scss/bootstrap.scss';
@import '../assets/style/vars.scss';


div{
  height: 80px;
  
  width: 100%;
  background-color: $primary-bg;

  img{
    margin: auto 10px;
    width: 55px;
    height: 55px;
  }
}

</style>
