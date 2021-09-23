<template>
  <header class="container-fluid">
    <div class="row d-flex align-items-center">
      <div class="col d-flex justify-content-between">
        <img src="../assets/spotify-icon.png" alt="">
        <select name="album" id="album">
            <option value="">Seleziona genere</option>
            <option value="">Rock</option>
            <option value="">Pop</option>
            <option value="">Jazz</option>
            <option value="">Metal</option>


        </select>
      </div>
    </div>
 </header>
</template>

<script>
export default {
  name: 'Header',
  props: ['infoAlbum']
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
