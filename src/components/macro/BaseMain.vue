<template>
    <main>

        <h2>FILMS</h2>
        <ul>
            <li v-for="movie in data.movies" :key="movie.id">
                <BaseCard :info="movie"/>

            </li>    
        </ul>
        <h2>SERIE TV</h2>
           <ul>
            <li v-for="tv in data.tv" :key="tv.id">
                <BaseCard :info="tv"/>
            </li>
        </ul>
    </main>
    </template>

<script>
import data from '../../shared/data';
import BaseCard from '../commons/BaseCard.vue';

export default {
    name: 'BaseMain',
    components: {
        BaseCard,
    },

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

<style lang='scss'>

    .flag {
        width: 20px;
    }

</style>