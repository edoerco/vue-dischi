<template>
<!-- creiamo la 'carta' contenente tutte le info dell'album -->
    <div class="album text-center">
        <img :src="info.poster" :alt="info.title">
        <h4 class="my-4">{{info.title}}</h4>
        <p class="m-0">{{info.author}}</p>
        <p class="m-0">{{info.year}}</p>
    </div>
</template>

<script>
export default {
    name: 'Album',
    props: ['info'],
}
</script>

<style scoped lang="scss" >
@import '../styles/vars';


.album {
    background-color: $primary;
    height: 380px;
    padding: 20px;
    max-width: 200px;

    img {
        width: 100%;
    }

    h4 {
        color: white;
    }

    p {
        color: grey
    }
}

// GRAZIE ALE <3
</style>>

