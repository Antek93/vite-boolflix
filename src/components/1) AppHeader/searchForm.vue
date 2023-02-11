<script>
import { store } from '../../store'
export default {
    name: 'searchForm', 
    data () {
        return {
            store
        }
    },
    created () {
        
    },
    methods: {
    }
};
</script>

<template>
    <div>
        <form action="#" @submit.prevent="$emit('search')">
            <input class="searchBar" type="text" v-model="store.userInput" placeholder="Search show">
            <button @keyup.click @keyup.enter class="ricerca" type="submit">
            Go!
             </button>
        </form>
    </div>
</template>

<style lang="scss">
@import '../../styles/partials/searchForm.scss'
</style>
