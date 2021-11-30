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

  data() {
    return {
      movieList: [],
    }
  },

  methods: {
    performSearch(searchText) {
      // console.log(searchText);

      if (searchText !== '') {
        console.log(searchText);
        axios.get('https://api.themoviedb.org/3/search/movie', {
          params: {
            api_key: 'f152fb9c2f42244ef45377bb1c3f3ca3',
            query: searchText,
            language: 'it-IT'
          }
        })
        .then( result => {
          this.movieList = [];
          this.movieList = result.data.results;
        })
        .catch( err => console.log(err) )
      }
    }
  }
}
</script>


<style lang="scss">

</style>
