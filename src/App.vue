<script>
// per importare axios 
import axios from 'axios';

import {store} from './store.js';

import AppHeader from './components/AppHeader.vue';

export default {
  data() {
    return {
      cards: [],

      store,
    }
  },

  components: {
    AppHeader,
  },

  created() {
    // spazio di codice che viene eseguito appena l'applicazione viene lanciata
    
    // da qui riempio il mio array con i dati delle carte
    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(res => {
        console.log(res.data)
        this.store.cards = res.data
        console.log(this.store.cards)
    })

  },

  methods: {


  },
}
</script>
<!-- ---------------------------------------------------------------------------------- -->
<template>

  <div>
    <AppHeader></AppHeader>
  </div>

</template>
<!-- ---------------------------------------------------------------------------------- -->
<style lang="scss">



</style>
