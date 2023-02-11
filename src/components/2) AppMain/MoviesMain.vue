<script>
import { store } from '../../store'
export default {
    name: 'MoviesMain', 
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
    }
  }
};
</script>

<template>
    <div v-for="element in this.store.moviesOutcome">           

            <div class="imgBox">
              <img :src="`https://image.tmdb.org/t/p/w342${element.backdrop_path}`"
              alt="">
            </div>

            <div>
             {{ element.title }}
            </div>

            <div>
             {{ element.original_title }}
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
              <span class="fi fi-um"></span>
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
.imgBox {
    width: 280px;
    height: 220px;
    background-image: url('../../assets/Immagine\ 2023-02-11\ 105702.png');
    background-size: cover;
    background-repeat: no-repeat;
    img {
    width: 100%;
    height: 100%;
  }
}

.space {
    height: 40px;
    width: 100%;
    background-color: aqua;
}
</style>
