<template>
  <div id="app">
    <div class="left-container"><Clock /></div>
    <div class="right-container"></div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HelloWorld from "./components/HelloWorld.vue";
import Clock from "./components/Clock.vue";

require('@/App.css')

@Component({
  components: {
    HelloWorld,
    Clock
  }
})
export default class App extends Vue {}
</script>

<style>
body {
  background-color: #2c3e50;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #EEE;
  margin-top: 60px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr ;
  gap: 1px 1px;
  grid-template-areas: ". .";
}

#left-container {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas: "." "." ".";
}

#right-container {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: 1fr 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas: "." "." "." ".";
}


</style>
