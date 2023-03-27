<script>
import axios from 'axios';
import card from './AppCardElement.vue';
export default {
    components: {
        card
    },
    data() {
        return {
            cards: []
        }
    },
    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((response) => {
                this.cards = response.data.data;
            })
    }
}
</script>

<template>
    <div class="container py-5">
        <div class="row mx-5">
            <article class="col-3 mb-4 text-center" v-for="card in cards.slice(0, 20)">
                <card :img="card.card_images[0].image_url" :name="card.name" :type="card.type" />
            </article>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.container{
    background-color: white;
}
</style>