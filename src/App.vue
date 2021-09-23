<template>
  <div>
    <Header />
    <Main @infoDisc="getInfoAlbum"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'


export default {
  name: 'App',
  data() {
    return {
      albumInfo: [],
    }
  },

  components: {
    Header,
    Main,
  },
  methods: {
    getInfoAlbum(infoDischi) {
      // console.log(infoDischi);
      this.albumInfo = infoDischi;
      console.log(this.albumInfo);
    }
  }
}
</script>

<style lang="scss">
@import "./styles/general.scss";
</style>
