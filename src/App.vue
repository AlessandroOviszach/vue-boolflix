<template>
  <div>
    <Header @search='performSearch' />

    <main>
      <CardList :list='movieList' />
      <CardList :list='tvList' />

    </main>
  </div>

</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue';
import CardList from '@/components/CardList.vue';

export default {
  name: 'App',

  components: {
    Header,
    CardList,
  },

  data() {
    return {
      movieList: [],
      tvList: [],
    }
  },

  methods: {
    performSearch(searchText) {
      const apiParams = {
        api_key: 'f152fb9c2f42244ef45377bb1c3f3ca3',
        query: searchText,
        language: 'it-IT',
      }

      if (searchText !== '') {
        // console.log(searchText);
        axios.get('https://api.themoviedb.org/3/search/movie', {
          params: apiParams,
        })
        .then( result => {
          this.movieList = [];
          this.movieList = result.data.results;
        })
        .catch( err => console.log(err) )
      


        axios.get('https://api.themoviedb.org/3/search/tv', {
          params: apiParams,
        })
        .then( result => {
          this.tvList = [];
          this.tvList = result.data.results;
        })
        .catch( err => console.log(err) )
      }
    }
  }
}
</script>


<style lang="scss">
* {
  font-family: sans-serif;
}
</style>