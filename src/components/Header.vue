<template>
  <header>
      <input
      type="text"
      placeholder="search a movie"
      v-model.trim="searchText"
      @keyup.enter="$emit('search', searchText)"
      >

      <button @click="$emit('search', searchText)">Search</button>
  </header>
  
</template>

<script>
export default {
  name : 'Header',
  data() {
    return {
      searchText : '',
    }
  }

}
</script>

<style scoped lang="scss">

</style>