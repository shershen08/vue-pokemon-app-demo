<template>
  <mt-header fixed :title="title"></mt-header>
</template>

<script>

import Vue from 'vue';
import Mint from 'mint-ui';
Vue.use(Mint);

import { Header } from 'mint-ui';
Vue.component(Header.name, Header);


export default {
  name: 'nav-bar',
  data () {
    return {
      title: 'Listing pokemons'
    }
  }
}
</script>


<style scoped>

</style>
