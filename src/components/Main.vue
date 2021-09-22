<template>
    <div class="container-fluid">
        <div class="row d-flex justify-content-center">
            <div v-for="(album, index) in AlbumList" :key="index" class="col-6 col-md-2 m-2">
                <!-- bisogna passargi 'info' con il v-bind per ciclare l'elemento Album -->
                <Album :info="album"/>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue'

export default {
    name: 'Main',
    components: {
        Album
    },
    data() {
        return {
           APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
    //    Questo array conterrà la lista delle canzoni
           AlbumList: [],
        }
    },
    created() {
        this.getAlbum();
    },
    methods: {
        getAlbum() {
            axios
                 .get(this.APIUrl)
                 .then( res => {
                     console.log(res.data.response);
                    this.AlbumList = res.data.response;
                 })         
        }
    }
}
</script>

<style scoped lang="scss" >
@import '../styles/vars';
.row {
    background-color: $secundary;
    padding: 50px;
}

</style>>
