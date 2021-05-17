<template>
  <div class="app">
    <PokeContainer />
  </div>
</template>

<script>
import PokeContainer from "@/components/PokeContainer";
export default {
  components: {
    PokeContainer,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@600;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@600;700&family=Raleway:ital,wght@0,400;0,500;1,400;1,500&display=swap");
.app {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: rgb(119, 110, 19);
  background: linear-gradient(
    45deg,
    rgba(119, 110, 19, 1) 0%,
    rgba(201, 179, 115, 1) 45%,
    rgba(186, 181, 131, 1) 100%
  );
}
</style>