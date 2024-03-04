<script>
export default {
    name: 'AppCardItem',

    props: {
        card: Object,
    },
}
</script>

<template>
    <li class="card">
        <img :src="card.card_images[0].image_url" :alt="card.name">
        {{ card.name }}
    </li>
</template>

<style lang="scss">

.card {
    display: flex;
    flex-direction: column;
    
    img {
        width: 200px;
    }
}


</style>