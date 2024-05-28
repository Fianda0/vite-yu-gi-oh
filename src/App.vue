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
      console.log(this.store.cards)
    })
  }
}

</script>

<template>

  <CardList />

</template>

<style scoped></style>
