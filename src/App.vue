<template>
  <div id="app">
    <Header :arrayGenres="arrayGenres"/>

    <div class="container">
      <Album :arrayAlbum="albumList" />
    </div>

  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import Album from '@/components/Album.vue';
export default {
  name: 'App',
  components: {
    Header,
    Album
  },
  data() {
      return {
          apiURL : 'https://flynn.boolean.careers/exercises/api/array/music',
          albumList : [],
          loading: true,
          arrayGenres: []

      }
  },
  created(){
      this.getAlbums();
  },
  methods: {
      getAlbums(){
          axios
              .get(this.apiURL)
              .then(res => {
                  let data = res.data.response;
                  this.albumList = data;
                  // console.log(data);
                  data.forEach(
                    (element) => {
                      if (!this.arrayGenres.includes(element.genre)) {
                        this.arrayGenres.push(element.genre);
                      }                      
                  });
                  // console.log(this.arrayGenres);
                  // this.loading = false;
                  })
      }
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

</style>
