<template>
    <header>
        <form @submit.prevent="searching">
            <input type="text" v-model="searchText" required>
            <button type="submit">CERCA</button>
        </form>
    </header>
</template>

<script>
import axios from 'axios'

export default {
    name: 'BaseHeader',
    data() {
        return {
            searchText: '',
        }
    },

    methods: {
        searching () {
            axios.get('https://api.themoviedb.org/3/search/movie',{

                params: {
                    api_key: 'e99307154c6dfb0b4750f6603256716d',
                    query: 'ritorno',
                    languade: 'it-IT'
                }

            }).then((response) => {
            this.films = response.data.results;
            }).catch((error) => {
            console.log(error);
            })
        }
    }
}




</script>

<style>

</style>


axios.get('https://api.themoviedb.org/3/search/movie',{
    params: {
        api_key: 'e99307154c6dfb0b4750f6603256716d',
        query: 'ritorno',
        languade: 'it-IT'
    }
}).then((response) => {
    this.films = response.data.results;
}).catch((error) => {
    console.log(error);
})
