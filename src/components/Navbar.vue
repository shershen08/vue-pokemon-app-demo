<template>
    <header>
        <OfflineIndicator></OfflineIndicator>
        <mt-header fixed :title="title"></mt-header>
    </header>
</template>

<script>

import Vue from 'vue';
import Mint from 'mint-ui';
Vue.use(Mint);

import { Header } from 'mint-ui';
Vue.component(Header.name, Header);

import { OfflineIndicator } from 'vue-online'

export default {
  name: 'nav-bar',
  data () {
    return {
      title: 'Listing pokemons'
    }
  },
  components :{
      OfflineIndicator
  }
}
</script>


<style scoped>

</style>
