<script>
import { store } from '../../store'
import MoviesMain from './MoviesMain.vue';
import SeriesMain from './SeriesMain.vue'

export default {
    name: 'AppMain', 
    data () {
        return {
            msg: 'Ciao',
            store,
        }
        
    },
    created () {
        
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
     <div>
        <MoviesMain />
        <SeriesMain />
    </div>
</template>

<style lang="scss">

</style>