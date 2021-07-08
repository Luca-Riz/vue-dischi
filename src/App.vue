<template>
  <div id="app">
    <Header />

    <div class="container">
      <Album />
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
