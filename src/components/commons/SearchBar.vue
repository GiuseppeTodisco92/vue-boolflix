<template>
  <div>
      <input v-model="shared.SearchText" type="text">
     
  </div>
</template>

<script>
import shared from "../../shared/shared";

export default {
    name: "SearchBar",
    data(){
      return{
        shared
        
      }
    }
}
</script>

<style lang="scss" scoped>

</style>