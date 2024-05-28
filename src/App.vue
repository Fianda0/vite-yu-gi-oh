<script>
import CardList from './components/CardList.vue';
import axios from 'axios';
import store from './data/store.js';


export default {
  components: {
    CardList
  },
  data() {
    return {
      store
    }
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0').then(risultato => {
      this.store.cards = risultato.data.data
    }),
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(risultato => {
        this.store.archetype = risultato.data
      })
  }
}

</script>

<template>
  <!-- <div v-for="element in this.store.archetype">{{ element.archetype_name }}</div> -->

  <header>
    <h1>{{ store.title }}</h1>
  </header>

  <select name="" id="">
    <option v-for="element in this.store.archetype" value="">{{ element.archetype_name }}</option>
  </select>

  <CardList />

</template>

<style scoped>
header {
  background-color: white;
  padding: 1rem;
  color: black;
}
</style>
