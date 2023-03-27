<script>
import { store } from '../store';
import card from './AppCardElement.vue';
export default {
    components: {
        card
    },
    data() {
        return {
            store
        }
    },

}
</script>

<template>
    <div v-for="card in store.card">
        <card :img="card.card_images[0].image_url" :name="card.name" :type="card.type" />
    </div>
</template>



<style lang="scss" scoped></style>