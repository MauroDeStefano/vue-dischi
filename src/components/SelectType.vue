<template>
    <select  class="selector" v-model="typeSelection" @change="getSelection">
      <option selected>metal</option>
      <option>jazz</option>
      <option>pop</option>
      <option>All</option>
    </select>  
</template>

<script>

export default{
  name: 'SelectType',
  data(){
    return {
    typeSelection : "",
    }
  },
  methods: {
    
  },
  computed:{
    getSelection(){
     return this.$emit("selectionType", this.typeSelection);
    }
  }
};

</script>

<style>
.selector{
  height: 30px;
  width: 100px
}
</style>
