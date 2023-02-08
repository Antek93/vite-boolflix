<script>
import { store } from '../../store'
export default {
    name: 'searchForm', 
    data () {
        return {
            variabileNome: '',
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
            <input type="text" v-model="store.userInput" placeholder="Search show">
            <button type="submit">
            Premi
             </button>
        </form>
    </div>
</template>

<style lang="scss">

</style>
