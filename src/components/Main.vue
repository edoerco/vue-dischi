<template>
    <div class="container-fluid">
        <div class="container">
            <div class="row d-flex justify-content-center">
                <div v-for="(album, index) in filteredList" :key="index" class="col-6 col-md-2 m-2">
                    <!-- bisogna passargi 'info' con il v-bind per ciclare l'elemento Album -->
                    <Album :info="album"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import Album from './Album.vue'

export default {
    name: 'Main',
    props:['userOptionsAlbum'],
    components: {
        Album
    },
    data() {
        return {
           APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
    //    Questo array conterrà la lista delle canzoni
           AlbumList: [],
           genreList: [],
        }
    },
    computed: {
        filteredList() {
            if(this.userOptionsAlbum == '') {
                return this.AlbumList
            } 
            else 
            {
            let filteredSongs = this.AlbumList.filter((element) => {
                if(element.genre == this.userOptionsAlbum) {
                    return element
                }
            }) 
            return filteredSongs;
            }
        }
    },

    created() {
        this.getAlbum();
        this.getGenre();

    },
    methods: {
        getAlbum() {
            axios
                .get(this.APIUrl)
                .then( res => {
                    // console.log(res.data.response);
                    this.AlbumList = res.data.response;
                    // console.log(this.AlbumList[0].genre)
                })         
        },

        getGenre() {
            axios
                .get(this.APIUrl)
                .then( res => {
                    // console.log(res.data.response);
                    for(let i=0; i < this.AlbumList.length; i++) {
                        let genre = res.data.response[i].genre
                        if(!this.genreList.includes(genre)) {
                            this.genreList.push(genre)
                        }
                    }
                    this.$emit('genreDisc', this.genreList);
                    // console.log(this.genreList);
                    // console.log(this.AlbumList[0].genre)
                }) 
            
        },
    }
}
</script>

<style scoped lang="scss" >
@import '../styles/vars';
.container-fluid {
    background-color: $secundary;
}

.row {
    padding: 50px 0;
}



</style>>
