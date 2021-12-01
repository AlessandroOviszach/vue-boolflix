<template>
  <header>
    <img src="@\assets\boolflix-logo.png" alt="">
    <div>
      <input
      type="text"
      placeholder="search a movie"
      v-model.trim="searchText"
      @keyup.enter="$emit('search', searchText)"
      >

      <button @click="$emit('search', searchText)">Search</button>
    </div>
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
  header {
    height: 10vh;
    background-color: #0d1117;
    display: flex;
    justify-content: space-between;

    div {
      margin-right: 5rem;
      height: 100%;
      display: flex;
      align-items: center;
      input {
        margin: 0 2rem;
        width: 300px;
      }

      button {
        padding: 0 1rem;
      }
    }
  }
</style>