<template>
  <div id="app">
    <Header :arrayGenres="arrayGenres" @getGenre="displayGenre" />

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
                  //sort ordina da a (piccolo) a b (grande) .year per mettere in ordine solo l'anno
                  data.sort(function(a, b) {
                    return a.year - b.year
                  });

                  this.albumList = data;
                  // console.log(data);
                  data.forEach(
                    (element) => {
                      if (!this.arrayGenres.includes(element.genre)) {
                        this.arrayGenres.push(element.genre);
                      }                      
                  });

                  })
      },
      displayGenre(genreSel){
        // console.log(genreSel);
        axios
            .get(this.apiURL)
            .then(res => {              
              let risposta = res.data.response;
              risposta.sort(function(a, b) {
                    return a.year - b.year
                  });
              // console.log(risposta, genreSel);
              if (genreSel === "all"){
                this.albumList = risposta;
              } else {
                this.albumList = risposta.filter(
                  (element) => {
                    return element.genre == genreSel;
                  }
                );
              }
            })
      }
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

</style>
