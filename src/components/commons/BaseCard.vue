<template>
    <div class="card">
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
    </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props: {
        info: Object,
    },
    data() {
        return {
            flagsAviable: [
                'en',
                'ja',
                'fr',
                'it',
                'es',
                'pt',
            ]
        }
    },
    computed: {
        vote() {
            return Math.ceil(this.info.vote_average / 2);
        }
    },
    methods: {
        existFlag(lang) {
            return this.flagsAviable.includes(lang);
        }
    }
}
</script>
<style lang='scss'>

    .flag {
        width: 20px;
    };

    .yellow {
        color: yellow;
    }

    body {
        background: grey;
    }
    
</style>