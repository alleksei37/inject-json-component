<template>
  <div class="hello">
    <h1>Hello World Sample</h1>
    <p>UserName: <b class="InjectedValue">{{json.UserName}}</b></p>
  </div>
</template>

<script>
export default {
  inject: {
    json: "json"
  },
  name: "HelloWorld",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
.InjectedValue {
  color: red;
}
</style>
