<template>
  <div class="hello">
   <poke-list></poke-list>
  </div>
</template>

<script>
import PokeList from './PokeList';

export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components : {
    'poke-list' : PokeList
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
