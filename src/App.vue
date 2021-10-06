<template>
  <div id="app">
    {{ message }}
    <List :pokemons="pokemons" />

  </div>

</template>

<script>
import List from './components/List.vue';
export default {
  name: 'App',
  components: {
    List
  },
  mounted() {
    this.getPockemon();
  },
  data() {
    return {
      message: "Hola Mundo",
      pokemons: ['charmander', 'charmilion']
    }
  },
  methods: {
    async getPockemon(){
      const res = await fetch("https://pokeapi.co/api/v2/pokemon?offset=15&limit=15");
      const data = await res.json();
      this.pokemons = data.results;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
