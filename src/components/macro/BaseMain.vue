<template>
  <main>
      <ul>
          <li v-for="movie in data.movies" :key="movie.id" :alt="movie.title">
              
              <img :src="urlImage(movie.poster_path)">
              <h2>{{movie.title}}</h2>
              <h3>{{movie.original_title}}</h3>
              <p>{{movie.vote_average}}</p>
              <p>{{movie.original_language}}</p>
              <h4><lang-flag :iso="movie.original_language"/></h4>
          </li>
      </ul>
  </main>
</template>

<script>
import data from '../../shared/data';

export default {
    name: 'BaseMain',
    data() {
        return {
            data,
        }
    },

    methods: {
        urlImage(url) {
            if (url === null) {
                return `https://via.placeholder.com/185x260`
            } 
            return `https://image.tmdb.org/t/p/w185/${url}`
        },
     
    }
}
</script>

<style>

</style>