<script setup>
const pokemon = defineProps(["name", "xp", "height", "img", "loading"])

</script>


<template>
        <div class="card cardPokemonSelected"
        :class="loading ? '' : 'animate__animated animate__flipInY'">
          <img 
          v-if="pokemon.name"
          :src="pokemon.img" 
          class="card-img-top pt-2" 
          height="250" 
          :alt="pokemon.name"
          >

          <img
          v-else src="../assets/egg.svg" 
          class="card-img-top pt-2" 
          height="250" 
          alt="???"
          >
          <div class="card-body">
            <h5 class="card-title text-center">{{pokemon.name || '???'}}</h5>
            <hr>
            <div class="row">
                <section class="col">
                    <strong>XP:</strong>
                    <span>{{pokemon.xp}}</span>
                </section>
                <section class="col">
                    <strong>Altura:</strong>
                    <span>{{pokemon.height}}</span>
                </section>
            </div>
          </div>
        </div>
</template>


<style scoped>

.cardPokemonSelected {
    height: 75vh;
    background-image: url(../assets/qualPokemon.png);
    background-size: 260% 100%;
}

</style>