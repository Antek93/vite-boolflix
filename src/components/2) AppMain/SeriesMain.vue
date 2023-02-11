<script>
import { store } from '../../store'
export default {
    name: 'SeriesMain', 
    data () {
        return {
            store,
        }
    },
    created () {
        
    },
    methods: {
      fromRatingTo(stars) {
        let newVote = stars;
        newVote = Math.ceil((stars / 2));
        return newVote
    },
    
  }
};
</script>

<template>
     
     <div v-for="element in this.store.seriesOutcome">
            <div class="imgBox">
              <img :src="`https://image.tmdb.org/t/p/w342${element.backdrop_path}`"
                   alt="../../assets/Immagine 2023-02-11 105702.png">
            </div>
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
              <i class="bi bi-star"></i>
            </div>

            <div>
                <!--Stampa tante stelle piene quanto il rating trasformato in quinti-->
                <span v-for="n in fromRatingTo(element.vote_average)">
                  &#9733; <!--Stella piena-->
                </span>

                <!--Stampa tante stelle vuoto quanto la differenza tra 5 (voto massimo) e il rating trasformato in quinti-->
                <span v-for="n in (5 - fromRatingTo(element.vote_average))">
                  &#9734;  <!--Stella vuota-->
                </span>
            </div>
      </div>
</template>

<style lang="scss">

</style>
