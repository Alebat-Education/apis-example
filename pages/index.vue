<script setup>
const ExampleAPIFetch = defineAsyncComponent(() =>
  import("@/components/ExampleAPIFetch.vue")
);
const ExampleAPIAxios = defineAsyncComponent(() =>
  import("@/components/ExampleAPIAxios.vue")
);
const ExampleAPIuseFetch = defineAsyncComponent(() =>
  import("@/components/ExampleAPIuseFetch.vue")
);
</script>

<template>
  <h1>Ejemplo de las APIs</h1>
  <!-- <ExampleAPIFetch /> -->
  <ExampleAPIAxios />
  <!-- <ExampleAPIuseFetch /> -->
</template>
