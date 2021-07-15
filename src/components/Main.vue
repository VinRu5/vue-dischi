<template>
    <main>
        <div class="container">
            <div class="row-me">
                <Loading v-if="albums.length < 10" />
                <Album v-for="(album, index) in albums" :key="index" 
                    :urlImg="album.poster"
                    :title="album.title"
                    :artist="album.author"
                    :year="album.year"
                    v-else
                />
            </div>
        </div>
    </main>
</template>

<script>
import Album from './Album.vue'
import Loading from './Loading.vue'

export default {
    name: 'Main',
    components: {
        Album,
        Loading
    },
    props: {
        albums: Array
    }
}
</script>

<style lang="scss" scoped>
@import '../style/_colors.scss';

    main {
        background-color: $back-color;
        padding-top: 80px;
        padding-bottom: 80px;

        .container {

            .row-me {
                display: flex;    
                flex-wrap: wrap;
                justify-content: center;
            }
        }
    }
</style>