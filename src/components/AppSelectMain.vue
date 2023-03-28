<script>
import { store } from '../store';
export default {
    data() {
    return {
      store
    }
  },
}
</script>


<template>
    <div class="container">
        <div class="row">
            <select class="w-25 form-select mx-5 my-4">
                <option selected>Selection type...</option>
                <option v-for="archetype in store.cards.slice(0,39)" value="alien">{{ archetype.archetype}}</option>
            </select>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>