<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <h1>{{message}}</h1>
    <AlbumViewer />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import AlbumViewer from "./components/AlbumViewer.vue";

export default {
  name: "app",
  data: () => ({
    message: "mozafar"
  }),
  components: {
    HelloWorld,
    AlbumViewer
  }
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
