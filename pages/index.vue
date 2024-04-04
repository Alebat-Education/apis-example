<script setup>
const ExampleAPI = defineAsyncComponent(() =>
  import("@/components/ExampleAPIFetch.vue")
);
</script>

<template>
  <h1>Ejemplo de las APIs</h1>
  <ExampleAPI />
</template>
