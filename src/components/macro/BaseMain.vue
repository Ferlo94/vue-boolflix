<template>
  <main>
      <ul>
          <li v-for="movie in data.movies" :key="movie.id">
              <h2>{{movie.title}}</h2>
              <h3>{{movie.original_title}}</h3>
              <p>{{movie.vote_average}}</p>
              <p>{{movie.original_language}}</p>
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
    }
}
</script>

<style>

</style>