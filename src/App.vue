<head>
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Inter">
</head>

<template>
  <div>
    <app-header></app-header>
    <app-start></app-start>
    <app-hello></app-hello>
    <app-card></app-card>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import HelloWorld from "./components/HelloWorld";
import Card from "./components/Card";
import Start from "./components/Start";

export default {
  components: {
    'app-header': Header,
    'app-hello': HelloWorld,
    'app-card': Card,
    'app-start': Start
  },
  data() {
    return {
    }
  }
}
</script>

<style>
#app {
  font-family: "Inter", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
body {
  margin: 0px;
  font-family: "Inter", sans-serif;
}
</style>
