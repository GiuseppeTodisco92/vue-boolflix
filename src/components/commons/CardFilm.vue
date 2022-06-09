<template>
  <div>
   <h1>{{filmCard.title}}</h1>
   <h2>{{filmCard.original_title}}</h2>
   <h3>{{filmCard.original_language}}</h3>
   <h4>{{filmCard.vote_average}}</h4>
  </div>
</template>

<script>
export default {
    name: "CardFilm",
    props:{
      filmCard:Object ,
    }
}
</script>

<style>

</style>