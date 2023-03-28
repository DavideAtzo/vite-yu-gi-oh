<script>
export default {
    name: 'card',
    props: {
        img: String,
        name: String,
        archetype: String,
    }
}
</script>

<template>
    <div class="img"><img class="img-fluid" :src="img"></div>
    <div class="text-box mx-2 pt-2 d-flex justify-content-between flex-column">
        <h6>{{ name }}</h6>
        <div class="d-flex justify-content-center align-items-baseline">{{ archetype }}</div>
    </div>
</template>


<style lang="scss" scoped>
@use '../assets/scss/variables/variables.scss' as *;
img {
    width: 200px;
}

.text-box {
    background-color: $primary;
    height: 130px;

    h6 {
        padding: 10px 0;
        font-size: 16px;
        font-weight: 600;
        text-transform: uppercase;
        color: white;
    }
}
</style>