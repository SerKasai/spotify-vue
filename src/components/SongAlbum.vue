<template>
  <div class="song-album">
    <figure class="album__image">
      <img :src="song.poster" alt="" />
      <div class="title">
        {{ song.title }}
      </div>
      <div class="info">
        {{ song.author }}
        <br />
        {{ song.year }}
        <!-- <br />
        {{ song.genre }} -->
      </div>
    </figure>
  </div>
</template>

<script>
export default {
  props: {
    song: {
      type: Object,
      require: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.song-album {
  display: flex;
  background-color: #253041;
  height: 250px;
  width: 150px;
  justify-content: center;
  figure {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;

    img {
      width: 120px;
      height: 120px;
    }
    .title {
      color: white;
      text-transform: uppercase;
      font-weight: 700;
    }
    .info {
      color: grey;
    }
  }
}
</style>
