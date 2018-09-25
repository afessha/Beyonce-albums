  <template>
  <div>
    <h3>{{subTitle}} </h3>
  <input type="text" v-model="search" placeholder="search by album"/>
    <v-layout row wrap>
        <v-flex v-for="(album) in filteredAlbums" :key="album.albumId" xs12>
            {{album.collectionName}}
        </v-flex>
    </v-layout>
    </div>
</template>

<script>
import axios from "axios";

export default {
  name: "AlbumViewer",
  data: () => ({
    albums: [],
    search: "",
    subTitle: "Beyonce Albums"
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
  },
  computed: {
    filteredAlbums: function() {
      return this.albums.filter(album => {
        return album.collectionName
          .toLowerCase()
          .match(this.search.toLowerCase());
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
input {
  border: 2px solid;
  margin: 25px;
}
</style>