<script>
export default {
    name: 'SingleCard',
    props: {
        elemento: array
    }
}
</script>

<template>
    <div class="col">
        <img :src="elemento.card_images[0].image_url" alt="">
    </div>
</template>

<style scoped></style>