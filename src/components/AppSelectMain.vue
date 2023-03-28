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
            <select class="w-25 form-select mx-5 my-4" v-model="store.searchArchetype" @change.prevent="$emit('selectInput')">
                <option selected>Selection type...</option>
                <option v-for="archetype in store.archetypes">{{ archetype.archetype_name }}</option>
            </select>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>