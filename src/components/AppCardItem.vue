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

    width: calc(100% / 5 - 40px / 5 * 4);
    background-color: #d48f38;

    border: 2px solid #212529;
    border-bottom-left-radius: 12px;
    border-bottom-right-radius: 12px;

    img {
        width: 100%;
        border-bottom: 2px solid #212529;
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