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
    <div class="container">
        <div class="row">
            <article class="text-center">
                <div class="img"><img class="img-fluid" :src="img"></div>
                <h5>{{ name }}</h5>
                <div>{{ type }}</div>
            </article>
        </div>
    </div>
</template>


<style lang="scss" scoped>
img {
    width: 200px;
}
</style>