<script>
import AppSelectMain from './AppSelectMain.vue';
    export default {
        components:{
            AppSelectMain
        }
    }
</script>


<template>
   <main>
    <AppSelectMain />
   </main>
</template>



<style lang="scss" scoped>
@use '../assets/scss/variables/variables.scss'  as *;

main{
    background-color: $primary;
    height: calc(100vh - 100px);
}
</style>