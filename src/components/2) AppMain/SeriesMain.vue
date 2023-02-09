<script>
import { store } from '../../store'
export default {
    name: 'SeriesMain', 
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
     
     <div v-for="element in this.store.seriesOutcome">
            <div>
             {{ element.name }}
            </div>

            <div>
             {{ element.original_name }}
            </div>

                <!-- SE italiano bandiera italiana -->
             <div v-if="element.original_language == 'it'">
              <span class="fi fi-it"></span>
            </div>
            <!--SE spagnolo bandiera spagnola-->
            <div v-if="element.original_language == 'es'">
              <span class="fi fi-es"></span>
            </div>
            <!--SE francese bandiera francese-->
            <div v-if="element.original_language == 'fr'">
              <span class="fi fi-fr"></span>
            </div>
            <!--SE tedesco bandiera tedesca-->
            <div v-if="element.original_language == 'de'">
              <span class="fi fi-de"></span>
            </div>
            <!--SE inglese bandiera americana-->
            <div v-if="element.original_language == 'en'">
              <span class="fi fi-um"></span>
            </div>
            <!--SE cinese bandiera cinese-->
            <div v-if="element.original_language == 'ch'">
              <span class="fi fi-cn"></span>
            </div>

            <div>
             {{ element.vote_average }}
            </div>
      </div>
</template>

<style lang="scss">

</style>
