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
            <div class="foundCards">
                <div>
                    Found 39 cards
                </div>
            </div>
            <article class="mb-4 text-center" v-for="card in cards.slice(0, 39)">
                <card :img="card.card_images[0].image_url" :name="card.name" :type="card.type" />
            </article>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../assets/scss/variables/variables.scss' as *;

.container {
    background-color: white;
    article{
        width: calc(100% / 5);
    }
    .foundCards {
        
        color: white;
        padding: 0 20px;
        div{
            background-color: $foundColor;
            padding: 30px 20px;
            font-weight: 600;
        }
    }
}</style>