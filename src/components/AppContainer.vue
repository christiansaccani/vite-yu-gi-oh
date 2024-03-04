<script>

import AppCardItem from './AppCardItem.vue';
import {store} from '../store.js';

export default {

    name: 'AppContainer',

    data() {
        return {
        cards: [],
        store,
        }
    },

    components:  {
        AppCardItem,
    },
}


</script>

<!-- ---------------------------------------------------------------------------------- -->

<template>

<main>
    <div id="container">
        <div id="black-line">
            Found N cards
        </div>
        <section id="cards-section">
            <ul>
                <AppCardItem 
                v-for="currentCard in store.cards.data"
                :card="currentCard">                
                </AppCardItem>
            </ul>
        </section>
    </div>
</main>

</template>

<!-- ---------------------------------------------------------------------------------- -->

<style lang="scss">

main {

    #container {
        margin: 120px auto;
        padding-top: 60px;

        width: 90vw;

        background-color: whitesmoke;

        #black-line {
            margin: 0 auto;
            padding: 30px 25px;
            width: 84vw;

            background-color: #212529;
            color: whitesmoke;

            font-weight: bold;
        }

        #cards-section {

            ul {
                display: flex;
                flex-flow: row wrap;
                justify-content: space-between;

                margin: 0 auto;
                padding: 30px 25px;
                width: 84vw;

                list-style: none;
            }
        }
    }
}

</style>
