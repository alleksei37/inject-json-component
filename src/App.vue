<template>
  <div id="app">
    <img width="25%" src="./assets/logo.png">
    <h1>InjectJson Component</h1>
    <InjectJson id="jsonTagId">
      <HelloWorld/>
    </InjectJson>
  </div>
</template>

<script>
import InjectJson from "./InjectJson";
import HelloWorld from "./components/HelloWorld";

export default {
  components: { InjectJson, HelloWorld }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
