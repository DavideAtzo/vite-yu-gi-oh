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
    data(){
    return {
      store
    }
  },
    created(){
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
                .then((response) => {
                    console.log(response);
                    this.store.cards = response.data.results;
                })
        }
  }
</script> 

<template>
  <AppHeader />
  <AppMain />
</template>


<style lang="scss">
</style>
