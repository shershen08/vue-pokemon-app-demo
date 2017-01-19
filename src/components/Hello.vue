<template>
  <div class="hello">
  <nav-bar/>
   <poke-list></poke-list>
  </div>
</template>

<script>
import PokeList from './PokeList';
import NavBar from './NavBar';

export default {
  name: 'hello',
  data () {
    return {}
  },
  components : {
    'poke-list' : PokeList,
    'nav-bar' : NavBar
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
