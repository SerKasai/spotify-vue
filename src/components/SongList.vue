<template>
  <section>
    <div class="container">
      <!-- <h2>Valore della props filtro ricevuta dal main content: {{ filtro }}</h2> -->
      <SongAlbum v-for="(song, i) in filteredGenre" :key="i" :song="song" />
    </div>
  </section>
</template>

<script>
import axios from "axios";
import SongAlbum from "./SongAlbum.vue";

export default {
  components: {
    SongAlbum,
  },
  data() {
    return {
      album: [],
    };
  },
  props: {
    filtro: {
      type: String,
      default: "",
    },
  },
  computed: {
    filteredGenre: function () {
      return this.album.filter((el) => {
        const { genre } = el;
        return genre.toLowerCase().includes(this.filtro.toLowerCase());
      });
    },
  },
  methods: {
    fetchAlbum: function () {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          console.log(res.data.response);
          this.album = res.data.response;
        });
    },
  },
  created() {
    this.fetchAlbum();
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  gap: 15px 30px;
  justify-content: center;
  flex-wrap: wrap;
  align-items: center;
}
</style>
