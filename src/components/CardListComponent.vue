<template>
   <div class="container">
        <div class="row">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3" v-for="(card, index) in store.cardList">
                {{ card.name }}
            </div>
        </div>
   </div>
</template>

<script>
import { store } from '../data/store.js';
    export default {
        name: 'CardListComponent',
        components: {

        }, 
        data() {
            return {
                store
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>