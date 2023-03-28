<script>
import AppSelectMain from './AppSelectMain.vue';
import AppCardList from './AppCardList.vue';
export default {
    components: {
        AppSelectMain,
        AppCardList
    },
    methods: {
        handleSearch() {
            this.$emit('select');
        }
    }
}
</script>


<template>
    <main>
        <AppSelectMain @selectInput="handleSearch"/>
        <AppCardList />
    </main>
</template>



<style lang="scss" scoped>
@use '../assets/scss/variables/variables.scss' as *;

main {
    background-color: $primary;
}
</style>