<script>
import store from '../data/store.js'
import SingleCard from './SingleCard.vue'


export default {
  name: 'CardList',
  components: {
    SingleCard
  },
  data() {
    return {
      store
    }
  }
}
</script>

<template>
  <!-- {{ store.dati[0].card_images[0].image_url }} -->



  <main>
    <div class="container">
      <div class="row justify-content-center">
        <SingleCard v-for="element in store.cards" :elemento="element" />
        <!-- <div v-for="element in store.dati">{{ element.card_images[0].image_url }}</div> -->
      </div>
    </div>
  </main>

</template>

<style scoped></style>
