  <template>
    <v-layout row wrap>
        <v-flex v-for="(album) in albums" :key="album.albumId" xs12>
            {{album.collectionName}}
        </v-flex>
    </v-layout>
</template>

<script>
import axios from "axios";

export default {
  name: "AlbumViewer",
  data: () => ({
    albums: []
  }),
  mounted() {
    this.getAlbums();
  },
  methods: {
    async getAlbums() {
      try {
        const { data } = await axios.get(
          "https://rawgit.com/rarmatei/f5ae92ac93d9716affab822a3f54f95b/raw/e62641b3f5ddd12c4fe34aa0912488224594e5a7/beyonce-albums.json"
        );

        this.albums = data;
      } catch (err) {
        this.error = true;
      }
    }
  }
};
</script>

<style>
</style>