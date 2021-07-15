<template>
  <div id="app">
    <Loading v-if="albums.length < 0" />
    <Header @choice="choiceGenre" />
    <Main :albums="filterAlbums" />

  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Loading from './components/Loading.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main,
    Loading
  },
  data() {
    return {
      albums: [],
      userChoice: '',
    }
  },
  computed: {
    filterAlbums() {

      return this.albums.filter((album) => {
          if (this.userChoice === 'all') {
          return true;
        }

        return album.genre.includes(this.userChoice);
      })
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
      this.albums = res.data.response;
    });
  },
  methods: {
    choiceGenre(select) {
      this.userChoice = select;
    }
  }
}
</script>

<style lang="scss">
@import './style/app.scss';
</style>
