<script setup>
// Fetch menos óptimo 1
const useFetchMeh = () => {
  fetch("https://pokeapi.co/api/v2/pokemon/")
    .then((response) => {
      if (!response.ok) {
        throw new Error("Network response was not ok");
      }
      return response.json(); // Convierte la respuesta a formato JSON
    })
    .then((data) => {
      // Maneja los datos recibidos
      console.log(data);
    })
    .catch((error) => {
      // Maneja errores
      console.error("Fetch error:", error);
    });
};
// Fetch menos óptimo 2
async function useFetchMehTwo() {
  fetch("https://pokeapi.co/api/v2/pokemon/")
    .then((response) => {
      if (!response.ok) {
        throw new Error("Network response was not ok");
      }
      return response.json();
    })
    .then((data) => {
      console.log(data);
    })
    .catch((error) => {
      console.error("Fetch error:", error);
    });
}
// Fetch más óptimo
async function useFetchGood() {
  try {
    const response = await fetch("https://pokeapi.co/api/v2/pokemon/");
    if (!response.ok) {
      throw new Error("Network response was not ok");
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Fetch error:", error);
  }
}

// Fetch con envio de datos a la API y respuesta(necesita api_key)
// Ver ejemplo en la web: https://es.libretranslate.com/
async function useFetchWithKey() {
  try {
    const response = await fetch("https://es.libretranslate.com/translate", {
      method: "POST",
      body: JSON.stringify({
        q: "hello world!",
        source: "en",
        target: "es",
        format: "text",
        api_key: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      }),
      headers: { "Content-Type": "application/json" },
    });
    if (!response.ok) {
      throw new Error("Network response was not ok");
    } else {
      const data = await response.json();
      console.log(data);
    }
  } catch (error) {
    console.error("Fetch error:", error);
  }
}

// Fetch con envio de datos a la API y respuesta
async function useFetchFive() {
  try {
    const response = await fetch("https://reqres.in/api/users", {
      method: "POST",
      body: JSON.stringify({
        name: "User 1",
      }),
      headers: { "Content-Type": "application/json" },
    });
    if (!response.ok) {
      throw new Error("Network response was not ok");
    } else {
      const data = await response.json();
      console.log(data);
    }
  } catch (error) {
    console.error("Fetch error:", error);
  }
}

useFetchMeh();

// useFetchMehTwo();

// useFetchGood();

// useFetchWithKey();

// useFetchFive()
</script>

<template></template>
