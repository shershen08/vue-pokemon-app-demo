<template>
  <div class="poke-list">
        <img class="poke-list__image" v-bind:src="selectedPokemonImage" v-if="selectedPokemonImage">
        <mt-progress :value="progressLevel" :bar-height="5"></mt-progress>
        <mt-index-list>
            <mt-cell :title="pokemon.name" v-for="pokemon in pokemons">
                <mt-button icon="more" type="default" @click="showPokemonDetails(pokemon)"></mt-button>
            </mt-cell>
        </mt-index-list>
  </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';

import Mint from 'mint-ui';
Vue.use(Mint);


import { IndexList, Progress, Button } from 'mint-ui';

Vue.component(Button.name, Button);
Vue.component(Progress.name, Progress);
Vue.component(IndexList.name, IndexList);

export default {
  name: 'poke-list',
  data () {
    return {
      pokemons: [],
      progressLevel: 0,
      selectedPokemonImage:''
    }
  },
   methods : {
      showPokemonDetails : function(itemData){
          this.progressLevel = 0;
          axios.get(itemData.url).then((item) => {
            this.selectedPokemonImage = item.data.sprites.front_default;
            this.progressLevel = 100;
        })
      }
  },
  mounted : function(){
      this.progressLevel = 30;
      axios.get('http://pokeapi.co/api/v2/pokemon/').then((list) => {
          this.pokemons = list.data.results;
          this.progressLevel = 80;
      })
  }
}
</script>


<style scoped>
    .poke-list__image {
        height: 200px;
    }
</style>
