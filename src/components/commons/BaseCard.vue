<template>
    <div class="card">
            <img :src="urlImage(info.poster_path)">
            <h2 v-if="info.title">{{info.title}}</h2>
            <h2 v-else>{{info.name}}</h2>
            <h3>{{info.original_title ? info.original_title : info.original_name}}</h3>
            <p>{{info.vote_average}}</p>
            <p> 
                <img class="flag" v-if="existFlag(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.png`)" :alt="info.original_language"> 
                <img class="flag" v-else src="../../assets/flags/lgbt.png" alt="lgbt">
            </p>
    </div>
</template>

<script>
export default {
    name: 'BaseCard',
    props: {
        info : Object,
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

    methods: {
        existFlag(lang) {
            return this.flagsAviable.includes(lang);
        }
    }
}
</script>

<style>

</style>