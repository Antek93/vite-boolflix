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
        getShow() {
            axios
                .get('https://api.themoviedb.org/3/search/movie?api_key=58a47dcf8326b213704d799954c33bd8&query=' + this.store.userInput)
                .then((response) => {
                        this.store.userOutcome = response.data.results
                        console.log(this.store.userOutcome)

                }
                )
        }
    },
    components: { SearchForm }
};

</script>

<template>
    <header>
        <div class="box container-fluid">
            <div>
                <h1>Boolfix</h1>
            </div>
            <div>
                <SearchForm @search="getShow" /> 
            </div>
        </div>
    </header>
</template>

<style lang="scss">
.box {
    height: 10vh;
}
</style>
