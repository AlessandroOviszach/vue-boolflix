<template>
  <div>
    <Header @search='performSearch' />
  </div>

</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';

export default {
  name: 'App',

  components: {
    Header,
  },

  methods: {
    performSearch(searchText) {
      // console.log(searchText);

      if (searchText !== '') {
        axios.get()
      }
    }
  }
}
</script>


<style lang="scss">

</style>
