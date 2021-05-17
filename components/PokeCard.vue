<template>
  <div class="poke-card">
    <a :href="card.url" class="card-info-poke">
      <img
        class="poke-img"
        :src="pokeImgUrl + card.id + '.svg'"
        :alt="'Image de ' + card.name"
      />
      <div class="poke-name">{{ card.name }}</div>
    </a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pokeImgUrl:
        "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/",
    };
  },
  props: {
    card: {
      type: Object,
      default: () => {},
    },
  },
};
</script>

<style scoped>
.poke-card {
  border: 1px white solid;
  background-color: rgba(255, 255, 255, 0.3);
  padding: 25px 5px 5px 5px;
  width: 125px;
  height: 125px;
  border-radius: 5px;
  cursor: pointer;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  align-items: center;
}

.poke-img {
  height: 50px;
  width: 50px;
  margin-bottom: 10px;
}

.poke-name {
  font-family: Raleway sans-serif;
  text-transform: capitalize;
  font-size: 21px;
  color: rgba(255, 255, 255, 0.8);
}
</style>