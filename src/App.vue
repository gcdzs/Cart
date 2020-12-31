<template>
  <div id="app">
    <Index />
  </div>
</template>

<script>
import Index from "./components/index.vue";

export default {
  name: "App",
  components: {
    Index,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  list-style: none;
}

body {
  font-size: 14px;
}

a {
  text-decoration: none;
}
</style>
