<template>
<div class="d-flex justify-content-between align-items-center">
    <img  src="https://cdn.discordapp.com/attachments/887685956050780201/913759060090843156/spotify-logo.png" alt="Logo">
    <SelectType 
    @selectionType="getType" />
</div>
</template>

<script>
import SelectType from './SelectType.vue'
export default {
  name: 'Header',
  components:{
    SelectType,
  },
  data(){
    return{
      selection : "",
    }
  },
  methods:{
   getType(text){
      this.selection = text;
      console.log("questo è getType dentro all'header", this.selection);
      return this.$emit("selectedType",this.selection);
    }
  },
  computed:{
     
  }

}
</script>

<style lang="scss" scoped>

@import '~bootstrap/scss/bootstrap.scss';
@import '../assets/style/vars.scss';


div{
  height: 80px;
  padding:  10px;
  width: 100%;
  background-color: $primary-bg;

  img{
    margin: auto 10px;
    width: 55px;
    height: 55px;
  }
}

</style>
