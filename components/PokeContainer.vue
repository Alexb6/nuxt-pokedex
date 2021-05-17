<template>
  <div class="container">
    <h1>Pokedex</h1>
    <PokeList :pokeUrls="allPokesUrls" />
  </div>
</template>

<script>
// import PokeSearch from "./PokeSearch";
import PokeList from "./PokeList";

export default {
  components: {
    // PokeSearch,
    PokeList,
  },
  created() {
    this.fetchFirstLevelData();
  },
  data() {
    return {
      apiUrl: "https://pokeapi.co/api/v2/pokemon/",
      prevLink: "",
      nextLink: "",
      allPokesUrls: [],
    };
  },
  methods: {
    async fetchFirstLevelData() {
      return await fetch(this.apiUrl)
        .then((res) => {
          return res.json();
        })
        .then((data) => {
          this.prevLink = data.previous;
          this.nextLink = data.next;
          data.results.map((poke) => this.allPokesUrls.push(poke.url));
        });
    },
  },
};
</script>

<style scoped>
h1 {
  font-size: 2.8rem;
  font-family: "Nunito", sans-serif;
  margin-bottom: 20px;
  color: #766722;
}
</style>