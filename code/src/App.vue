<template>
  <h1>Hello to Home Page</h1>
  <HelloWorld></HelloWorld>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
export default {
  components: { HelloWorld },
};
</script>

<style scoped>
h1 {
  text-align: center;
}
</style>
