<template>
  <main>
    <div class="container">
      <SelectGenre @filter="setGenre" />
      <!-- <p>Valore di stringaFiltro: {{ stringaFiltro }}</p> -->
      <figure class="album">
        <SongList :filtro="stringaFiltro" />
      </figure>
    </div>
  </main>
</template>

<script>
import SelectGenre from "./SelectGenre.vue";
import SongList from "./SongList.vue";
export default {
  components: {
    SongList,
    SelectGenre,
  },
  data() {
    return {
      stringaFiltro: "",
    };
  },
  methods: {
    setGenre: function (select) {
      this.stringaFiltro = select;
      console.log("Ho ascoltato l'evento filter e il dato è:" + select);
    },
  },
};
</script>

<style lang="scss" scoped>
main {
  height: 831px;

  .container {
    background-color: #1a222e;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    .album {
      display: flex;
      justify-content: space-evenly;
      height: 100%;
      align-items: center;
      width: 50%;
    }
  }
}
</style>
