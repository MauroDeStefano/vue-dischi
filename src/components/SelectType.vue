<template>
    <select  class="selector" v-model="typeSelection" @change="$emit('selectionType', typeSelection)">
      <option>metal</option>
      <option>jazz</option>
      <option>pop</option>
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
    getSelection(){
      this.$emit("selectionType", this.typeSelection);
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
