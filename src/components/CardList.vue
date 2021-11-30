<template>
  <section>
      <div 
      class="col"
      v-for='item in list'
      :key='item.id'
      >

      <Card
      :title='item.title'
      :originaltitle='item.original_title'
      :language='item.original_language'
      :vote='item.vote_avarage'
      />
        <!-- <div class="card">
          <ul>
            <li>Titolo: {{ item.title }} </li>
            <li>Titolo Originale: {{ item.original_title }} </li>
            <li>Lingua: {{ item.original_language }} </li>
            <li>Voto: {{ item.vote_avarage }} </li>
          </ul>
        </div> -->
      </div>
  </section>
</template>

<script>
import Card from '@/components/Card.vue'

export default {
  name : 'CardList',

  components : {
    Card,
  },

  props : {
    list : Array,
  },
}
</script>

<style scoped lang='scss'>

</style>e