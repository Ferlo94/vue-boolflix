<template>
    <main>
<<<<<<< HEAD
        <section>
            <h2>Films</h2>
            <ul>
                <li v-for="movie in data.movies" :key="movie.id">
                    <BaseCard :info="movie"/>
                </li>
            </ul>
        </section>
        <section>
            <h2>Serie TV</h2>
            <ul>
                <li v-for="tv in data.tv" :key="tv.id">
                    <BaseCard :info="tv"/>
                </li>
            </ul>
        </section>
=======

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
>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
    </main>
</template>

<script>
import data from '../../shared/data';
import BaseCard from '../commons/BaseCard.vue';
<<<<<<< HEAD
export default {
    name: 'BaseMain',
    components: {
        BaseCard
    },
    data() {
        return {
            data,
        }
    },
=======

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
>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
}
</script>