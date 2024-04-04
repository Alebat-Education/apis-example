<script setup>
const {
  data: fetchedPokemon,
  pending,
  error,
} = useFetch("https://pokeapi.co/api/v2/pokemon/1");

const pokemon = computed(() => fetchedPokemon.value);

console.log(pokemon.value);
</script>

<template>
  <p v-if="pending">Cargando...</p>
  <p v-else-if="error">Error al cargar los datos.</p>
  <section v-if="pokemon">
    <h2>{{ pokemon.name }}</h2>
  </section>
</template>
