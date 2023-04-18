<template>
  <div>
    <CardListComponent/>
  </div>
</template>

<script>
import { store } from './data/store';
import axios from 'axios';
import CardListComponent from './components/CardListComponent.vue';
  export default {
    name: 'App',
    components: {
      CardListComponent,
    },
    data() {
      return {
        store,
      }
    },
    methods: {
      getCards() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {
          console.log(res.data.data);
          store.cardList = res.data.data;
        })
      }
    },
    mounted() {
      this.getCards();
    }
  }
</script>

<style lang="scss" scoped>

</style>
