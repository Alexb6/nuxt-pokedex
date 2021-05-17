<template>
  <div class="poke-list">
    <div class="poke-list-list">
      <PokeCard v-for="poke in allPokes" :key="poke.id" :card="poke" />
    </div>
    <div class="poke-list-nav">
      <button type="button" class="nav-prev">Previous</button>
      <button type="button" class="nav-next">Next</button>
    </div>
  </div>
</template>

<script>
import PokeCard from "./PokeCard";

export default {
  components: {
    PokeCard,
  },
  fetch() {
    this.fetchAllPokesData();
  },
  props: {
    pokeUrls: Array,
  },
  data() {
    return {
      allPokes: [],
    };
  },
  methods: {
    async fetchAllPokesData() {
      return await this.pokeUrls.map((pokeUrl) => {
        fetch(pokeUrl)
          .then((res) => {
            return res.json();
          })
          .then((poke) => this.allPokes.push(poke));
      });
    },
  },
};
</script>

<style scoped>
.poke-list-list {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  column-gap: 12px;
  row-gap: 12px;
  margin-bottom: 25px;
}

.poke-list-nav {
  display: flex;
  justify-content: space-around;
}

button {
  height: 35px;
  width: 130px;
  padding: 0;
  border: none;
  border-radius: 3px;
  font-size: 1.3rem;
  font-family: "Nunito", sans-serif;
  background-color: #766722;
  color: white;
  cursor: pointer;
}
</style>