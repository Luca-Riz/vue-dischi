<template>
  <div id="app">
    <Header message="Prova titolo"/>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style lang="scss">
@import '@/style/general.scss';

</style>
