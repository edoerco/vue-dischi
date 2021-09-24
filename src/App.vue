<template>
  <div>
    <Header 
    :genreAlbum="albumGenre"
    @selectedOption="getOption" />

    <Main 
    @genreDisc="getGenreAlbum"
    :userOptionsAlbum="userOptions"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'


export default {
  name: 'App',
  data() {
    return {
      albumGenre: [],
      userOptions: "",
    }
  },

  components: {
    Header,
    Main,
  },
  methods: {
    getGenreAlbum(genreDischi) {
      // console.log(infoDischi);
      this.albumGenre = genreDischi;
      // console.log(this.albumGenre)
      // console.log(this.albumInfo);
    },
    getOption(text) {
      this.userOptions = text
      console.log(text)
    }
  },
}
</script>

<style lang="scss">
@import "./styles/general.scss";
</style>
