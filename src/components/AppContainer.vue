<script>

import axios from 'axios';

import AppCardItem from './AppCardItem.vue';
import {store} from '../store.js';
import CardSearch from './CardSearch.vue';



export default {

    name: 'AppContainer',

    data() {
        return {
        cards: [],
        store,

        foundCards: store.cards.data,
        searchTerm: '',
        }
    },

    components:  {
        AppCardItem,
        CardSearch,
    },

    methods: {
        searchCard(searchText) {
            axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&fname=${searchText}`)
            .then(res => {
                console.log(res.data);
                this.store.cards = res.data;
                console.log(this.store.cards);
            })
            .catch(error => {
                console.error('Errore durante la ricerca delle carte:', error);
            });
        },
    }
}


</script>

<!-- ---------------------------------------------------------------------------------- -->

<template>

<main>
    <div id="container">
        <CardSearch @search="searchCard"></CardSearch>
        <div id="black-line">
            {{ (store.cards.data || []).length > 0 ? 'Found ' + (store.cards.data || []).length + ' cards' : 'Loading...' }}
            
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

                gap: 40px;
                row-gap: 1em;

                margin: 0 auto;
                padding-bottom: 30px;
                width: 84vw;

                list-style: none;
            }
        }
    }
}

</style>
