<script>
import SearchForm from './searchForm.vue'
import axios from 'axios'
import { store } from '../../store'


export default {
    name: "AppHeader",
    data() {
        return {
            msg: "Ciao",
            store
        };
    },
    created() {
    },
    methods: {
        getMovies() {
            axios
                .get('https://api.themoviedb.org/3/search/movie?api_key=58a47dcf8326b213704d799954c33bd8&query=' + this.store.userInput)
                .then((response) => {
                        this.store.moviesOutcome = response.data.results
                        console.log('movies', this.store.moviesOutcome)

                }
                )
        
            axios
                .get('https://api.themoviedb.org/3/search/tv?api_key=58a47dcf8326b213704d799954c33bd8&query=' + this.store.userInput)
                .then((response) => {
                        this.store.seriesOutcome = response.data.results
                        console.log('series', this.store.seriesOutcome)


                }
                )
    }
    },
    components: { SearchForm }
};

</script>

<template>
    <header>
        <div class="box container-fluid bg-dark d-flex justify-content-between align-items-center">
            <div>
                <h1 class="px-2">
                    Boolfix
                </h1>
            </div>
            <div class="px-2">
                <SearchForm @search="getMovies" /> 
            </div>
        </div>
    </header>
</template>

<style lang="scss">
@import '../../styles/partials/AppHeaderAttributes.scss'
</style>

