<template>
  <div class="poke-list">
      {{JSON.stringify(pokemons)}}
  </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';


export default {
  name: 'poke-list',
  data () {
    return {
      pokemons: [],
      progressLevel: 0
    }
  },
  methods : {
     
  },
  mounted : function(){
      axios.get('http://pokeapi.co/api/v2/pokemon/').then((list) => {
          this.pokemons = list.data.results;
          this.progressLevel = 80;
      })
  }
}
</script>


<style scoped>

</style>
