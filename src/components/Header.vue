<template>
  <header class="container-fluid">
    <div class="row d-flex align-items-center">
      <div class="col">
        <img src="../assets/spotify-icon.png" alt="">
      </div>
    </div>
 </header>
</template>

<script>
export default {
  name: 'Header',
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
