<script>
import axios from 'axios';
import { store } from './store';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
  components: {
    AppHeader,
    AppMain
  },
  data() {
    return {
      store
    }
  },
  methods: {
    search(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response) => {
        console.log(response);
        this.store.cards = response.data.data;
      }),
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
          this.store.archetypes = response.data;
        })
    }
  },
  created() {
    this.search();
  }
}
</script> 

<template>
  <AppHeader />
  <AppMain @select="search"/>
</template>


<style lang="scss"></style>
