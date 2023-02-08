<script>
import { store } from '../../store'
export default {
    name: 'AppMain', 
    data () {
        return {
            msg: 'Ciao',
            store,
            languageDetected: '', 
        }
    },
    created () {
        
    },
    methods: {
        flag () {
            if (this.languageDetected = 'en') {
            } else if (this.languageDetected = 'it') {

            } else if (this.languageDetected = 'de') {

            } else if (this.languageDetected = 'fr') {

            }
        }
    }
};
</script>

<template>
     <div>
        <div v-for="element in this.store.userOutcome">
            <div>
             {{ element.title }}
            </div>

            <div>
             {{ element.original_title }}
            </div>

            <!--SE italiano bandiera italiana-->
            <div v-if="element.original_language == 'it'">
              <span id="1" class="fi fi-it"></span>
            </div>
            <!--Se spagnolo bandiera spagnola-->
            <div v-if="element.original_language == 'es'">
              <span id="1" class="fi fi-es"></span>
            </div>
            <!--SE francese bandiera francese-->
            <div v-if="element.original_language == 'fr'">
              <span id="1" class="fi fi-fr"></span>
            </div>
            <!--SE tedesco bandiera tedesca-->
            <div v-if="element.original_language == 'de'">
              <span id="1" class="fi fi-de"></span>
            </div>
            <!--SE inglese bandiera americana-->
            <div v-if="element.original_language == 'en'">
              <span id="1" class="fi fi-um"></span>
            </div>
            <!--SE cinese bandiera cinese-->
            <div v-if="element.original_language == 'ch'">
              <span id="1" class="fi fi-cn"></span>
            </div>

            <div>
             {{ element.vote_average }}
            </div>
        </div>
    </div>
</template>

<style lang="scss">

</style>
