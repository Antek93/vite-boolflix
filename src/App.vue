<script>
import AppHeader from './components/1) AppHeader/Appheader.vue'
import AppMain from './components/2) AppMain/AppMain.vue'
import axios from 'axios'
import { store } from './store.js'

export default {
    name: 'ciao',
    data () {
        return {
            msg: 'Ciao',
            store
        }
    },
    created () {
        
    },
    methods: {
    },
    components: {
      AppHeader,
      AppMain,
    }
};
</script>

<template>
  <AppHeader/>
  <AppMain />
</template>

<style lang="scss">
@use './styles/main.scss' as *;
</style>
