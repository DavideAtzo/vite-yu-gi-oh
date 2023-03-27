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
    <div class="container">
        <div class="row ">
            <div v-for="card in cards.slice(0,20)">
                <card :img="card.card_images[0].image_url" :name="card.name" :type="card.type" />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
img{
    width: 200px;
}
</style>