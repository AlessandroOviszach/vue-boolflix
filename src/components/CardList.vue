<template>
  <section>
      <div 
      class="col"
      v-for='item in list'
      :key='item.id'
      >
        <div class="card">
          <ul>
            <li>Titolo: {{ item.title }} </li>
            <li>Titolo Originale: {{ item.original_title }} </li>
            <li>Lingua: {{ item.original_language }} </li>
            <li>Voto: {{ item.vote_avarage }} </li>
          </ul>
        </div>
      </div>
  </section>
</template>

<script>
export default {
  name : 'CardList',
  props : {
    list : Array,
  }
}
</script>

<style scoped lang='scss'>

</style>e