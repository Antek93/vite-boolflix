<script>
import { store } from '../../store'
import MoviesMain from './MoviesMain.vue';
import SeriesMain from './SeriesMain.vue'

export default {
    name: 'AppMain',
    data() {
        return {
            msg: 'Ciao',
            store,
        }

    },
    created() {

    },
    methods: {
    },
    components: {
        MoviesMain,
        SeriesMain
    }
};
</script>

<template>
    <div class="mainContainer px-2">
        <div>
            <h4 class="px-2">
                Movies
            </h4>
        </div>
        <div class="movieSection d-flex align-items-center justify-content-between">
            <MoviesMain />
        </div>
        <div>
            <h4 class="px-2">
                Tv Series
            </h4>
        </div>
        <div class="serieSection d-flex align-items-center justify-content-between">
            <SeriesMain />
        </div>
    </div>
</template>

<style lang="scss">
@import '../../styles/partials/AppMainAttributes.scss'
</style>