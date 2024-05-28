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
      store,
      valore: '',
    }
  },
  methods: {
    getArchetype() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0&archetype=' + this.valore).then(risultato => {
        this.store.cards = risultato.data.data
      })
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

  <header>
    <h1>{{ store.title }}</h1>
  </header>

  <section id="selezione">

    <select v-model="valore">

      <option disabled>Scegli un archetype</option>
      <option v-for="element in this.store.archetype">{{ element.archetype_name }}</option>

    </select>

    <button @click="getArchetype">Cerca per Archetype</button>
  </section>

  <CardList />

</template>

<style scoped>
header {
  background-color: white;
  padding: 1rem;
  color: black;
  margin-bottom: 2rem
}

#selezione {
  text-align: center;
  padding: 1rem;
}
</style>
