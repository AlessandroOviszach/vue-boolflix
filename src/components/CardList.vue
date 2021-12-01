<template>
  <section>
      <div 
      class="col"
      v-for='item in list'
      :key='item.id'
      >

      <Card
      :title='item.title ? item.title : item.name'
      :originaltitle='item.original_title ? item.original_title : item.original_name'
      :language='item.original_language'
      :vote='item.vote_avarage'
      :poster='item.poster_path'
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

<style scoped lang='scss'></style>