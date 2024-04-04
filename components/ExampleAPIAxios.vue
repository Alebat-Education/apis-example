<script setup>
import axios from "axios";

const endpoint = "https://pokeapi.co/api/v2/pokemon/ditto";

const retrieveData = async () => {
  try {
    const response = await axios.get(endpoint);

    // En este punto, response ya tiene los datos de la Api, y no hay que transformar la respuesta a JSON, ya que se hace automáticamente

    return response;
  } catch (error) {
    return error;
  }
};

const { data } = await retrieveData();

// data.name equivale a "ditto" o al error, dependiendo de si la llamada se ha realizado correctamente o no
</script>

<template>
  <h2>{{ data.name }}</h2>
</template>
