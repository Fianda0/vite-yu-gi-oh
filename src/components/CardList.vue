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

  <header>
    <h1>{{ store.title }}</h1>
  </header>

  <main>
    <div class="container">
      <div class="row">
        <SingleCard v-for="element in store.dati" :elemento="element" />
        <!-- <div v-for="element in store.dati">{{ element.card_images[0].image_url }}</div> -->
      </div>
    </div>
  </main>

</template>

<style scoped>
header {
  background-color: white;
  padding: 1rem;
  color: black;
}
</style>
