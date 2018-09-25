<template>
  <v-app>
      <v-toolbar app>
          <v-toolbar-title>Beyonce App</v-toolbar-title>
      </v-toolbar>
      <v-content>
        <AlbumViewer />
      </v-content>
      <v-footer>
        ©Awet 2018
      </v-footer>
  </v-app>
</template>

<script>
import AlbumViewer from "./components/AlbumViewer.vue";

export default {
  components: {
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
