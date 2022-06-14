<template>
    <div class="card">
<<<<<<< HEAD
        <img v-if="info.poster_path" :src="`https://image.tmdb.org/t/p/w342${info.poster_path}`" :alt="info.title">
        <img v-else src="https://via.placeholder.com/342x482" alt="">
        <h3 v-if="info.title">{{info.title}}</h3>
        <h3 v-else>{{info.name}}</h3>
        <h4>{{info.original_title ? info.original_title : info.original_name}}</h4>
        <p>{{vote}}</p>
        <i v-for="n in vote" :key="'solid-'+n" class="fa-star fa-solid yellow"></i>
        <i v-for="n in 5 - vote" :key="'regular-'+n" class="fa-star fa-regular yellow"></i>
        <p>
            <img class="flag" v-if="existFlag(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language">
            <img width="30" v-else src="../../assets/flags/pace.png" alt="Pace">
        </p>
=======
            <img :src="urlImage(info.poster_path)">
            <h2 v-if="info.title">{{info.title}}</h2>
            <h2 v-else>{{info.name}}</h2>
            <h3>{{info.original_title ? info.original_title : info.original_name}}</h3>
            <p>{{info.vote_average}}</p>
            <p> 
                <img class="flag" v-if="existFlag(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language"> 
                <img class="flag" v-else src="../../assets/flags/lgbt.png" alt="lgbt">
            </p>
>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
    </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props: {
<<<<<<< HEAD
        info: Object,
=======
        info : Object,
>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
    },
    data() {
        return {
            flagsAviable: [
<<<<<<< HEAD
=======

>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
                'en',
                'ja',
                'fr',
                'it',
                'es',
                'pt',
            ]
        }
    },
<<<<<<< HEAD
    computed: {
        vote() {
            return Math.ceil(this.info.vote_average / 2);
        }
    },
=======

>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
    methods: {
        existFlag(lang) {
            return this.flagsAviable.includes(lang);
        }
    }
}
</script>
<<<<<<< HEAD
<style lang='scss'>

    .flag {
        width: 20px;
    };

    .yellow {
        color: yellow;
    }

    body {
        background: lightgrey;
    }
    
=======

<style>

>>>>>>> 1b27e4face55c1afbfcf4ef10ca4799beb07b9b0
</style>