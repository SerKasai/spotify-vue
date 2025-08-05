<template>
  <div class="select">
    <label for="select-genre">Filtra ricerca...</label>

    <select
      name="genre"
      id="select-genre"
      v-model="genere"
      @click="$emit('filter', genere)"
    >
      <option value="">--Scegli un genere--</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
    <button class="button-reset" @click="genere = ''">Reset</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      genere: "",
    };
  },
  methods: {
    filtraGenere: function () {
      console.log(this.genere);
      this.$emit("filtra", this.genere); // alternativa con methods //
    },
  },
};
</script>

<style lang="scss" scoped>
.select {
  padding: 30px;

  #select-genre {
    padding: 0 10px;
    margin: 0 10px;
  }
  button {
    padding: 5px;
  }
}
</style>
