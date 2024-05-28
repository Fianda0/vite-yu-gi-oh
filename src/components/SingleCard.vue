<script>
export default {
    name: 'SingleCard',
    props: {
        elemento: Object
    },
}
</script>

<template>
    <div class="col-3 card">
        <img :src="elemento.card_images[0].image_url" alt="">
        <h4 class="p-3">{{ elemento.name }}</h4>
        <span class="p-2">{{ elemento.archetype }}</span>
    </div>
</template>

<style scoped>
img {
    width: 100%;
}

.card {
    background-color: orange;
    text-align: center;
    padding: 0.5rem;
    margin: 0.5rem;
}
</style>