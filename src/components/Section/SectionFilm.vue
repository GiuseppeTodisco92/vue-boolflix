<template>
  <section>
   
    <button @click="FilmsFilter()">search</button>
    <ul>
      <li v-for="film in films" :key="film.id"><card-film :filmCard = "film" /></li>
      
    </ul>
  </section>
</template>

<script>

import CardFilm from '../commons/CardFilm.vue'
import axios from "axios";

import shared from "../../shared/shared";

export default {
  
    name: "SectionFilm",
    components: { 
        CardFilm
         },
          data() {
            return {
              shared,
              films: [],
            }
      },

    methods:{
       FilmsFilter() {
      axios.get('https://api.themoviedb.org/3/search/movie', {
        params: {
          api_key: '4b0c28a1bd3d6957da805de5fa061ed1',
          query: shared.SearchText,
          language: this.films.original_language,
          vote: this.films.vote_average,
        }
      }).then((response) => {
        this.films = response.data.results;
        console.log(this.films);
      }).catch((error) => {
        console.log(error);
      })
    },

    }
   
      
}
</script>

<style>

</style>