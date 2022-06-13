<template>
  <main>
      <ul>
          <li v-for="movie in data.movies" :key="movie.id" :alt="movie.title">
              
              <img :src="urlImage(movie.poster_path)">
              <h2>{{movie.title}}</h2>
              <h3>{{movie.original_title}}</h3>
              <p>{{movie.vote_average}}</p>
              <p> <img class="flag" :src="existFlag(movie.original_language) ? require(`../../assets/flags/${movie.original_language}.png`) : null "> </p>
              
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
            flagsAviable: [

                'en'
            ]
        }
    },


    methods: {
        urlImage(url) {
            if (url === null) {
                return `https://via.placeholder.com/185x260`
            } 
            return `https://image.tmdb.org/t/p/w185/${url}`
        },
        existFlag(lang) {
            return this.flagsAviable.includes(lang);
        }
     
    }
}


</script>

<style lang='scss'>

    .flag {
        width: 20px;
    }

</style>