<template>
  <div id="app">
    <Header />

    <div class="container">
        <div class="row row-cols-2 row-cols-md-4 row-cols-lg-5">
          <Album />
          

        </div>
    </div>



  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Album from '@/components/Album.vue';

export default {
  name: 'App',
  components: {
    Header,
    Album
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

</style>
