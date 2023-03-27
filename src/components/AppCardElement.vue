<script>
    export default {
        name: 'card',
        props: {
            img: String,
            name: String,
            type: String,
        }
    }
</script>


<template>
    <article class="text-center">   
        <div class="img"><img class="img-fluid" :src="img"></div>
        <h5>{{  name }}</h5>
        <div>{{ type }}</div>
    </article>
</template>


<style lang="scss" scoped>
</style>