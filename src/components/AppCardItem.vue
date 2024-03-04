<script>
export default {
    name: 'AppCardItem',

    props: {
        card: Object,
    },
}
</script>

<template>
    <li class="my_card">
        <img :src="card.card_images[0].image_url" :alt="card.name">
        <p class="card-name">{{ card.name }}</p>
        <p class="card-race">{{ card.race }}</p>
    </li>
</template>

<style lang="scss">

.my_card {
    display: flex;
    flex-direction: column;
    align-items: center;

    gap: 1em;
    padding-bottom: .5em;

    background-color: #d48f38;

    img {
        width: 15vw;
    }

    .card-name {
        color: whitesmoke;
        font-size: large;
        font-weight: bold;
        text-align: center;

        max-width: 13vw;
    }

    .card-race {
        color: black;
        font-size: large;
        font-weight: bold;
        text-align: center;

        max-width: 14vw;
    }
}


</style>