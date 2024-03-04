<script>
// per importare axios 
import axios from 'axios';

export default {
  data() {
    return {

    }
  },

  created() {
    // spazio di codice che viene eseguito appena l'applicazione viene lanciata
    
    axios
      .get('https://rickandmortyapi.com/api/character?page=1')
      .then(res => {
        console.log(res.data.results)
        this.store.characters = res.data.results
    }).catch(err => {
      console.log(err)
    })

  },

  components: {
    
  },

  methods: {


  },
}
</script>
<!-- ---------------------------------------------------------------------------------- -->
<template>



</template>
<!-- ---------------------------------------------------------------------------------- -->
<style lang="scss">



</style>
