<template>
  <header class="container-fluid">
    <div class="row d-flex align-items-center">
      <div class="col d-flex justify-content-between">
        <img src="../assets/spotify-icon.png" alt="">
        <select v-model="selectedText" @change="$emit('selectedOption', selectedText)" name="album" id="album">
            <option value="">Seleziona genere</option>
            <option v-for="(genre, index) in genreAlbum" :key="index" :value="genre">{{genre}}</option>
            


        </select>
      </div>
    </div>
 </header>
</template>

<script>
export default {
  name: 'Header',
  props: ['genreAlbum'],
  data() {
    return {
      selectedText: '',
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
// importiamo gli stili salvati nel file vars
@import '../styles/vars';

.row {
  background-color: $primary;
  height: 70px;

  img {
    width: 40px;
  }
}
</style>
