<template>
  <main>
    <div class="container">
      <figure class="album">
        <SongList />
      </figure>
    </div>
  </main>
</template>

<script>
import SongList from "./SongList.vue";
export default {
  components: {
    SongList,
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
