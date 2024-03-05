<script>
    import axios from 'axios';

    import {store} from '../store.js';

    export default {
        name: 'CardArcFilter',

        data() {
            return {
                store,
            }
        },

        methods: {
            applyFilter(event) {
                this.store.cards = [];
                const selectedArchetype = event.target.value;
                axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=${selectedArchetype}`)
                    .then(res => {
                        console.log(res.data);
                        this.store.cards = res.data;
                    })
                    .catch(error => {
                        console.error('Errore durante il recupero delle carte:', error);
                    });      
            }
        },
    
        created() {
            axios
                .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
                .then(res => {
                    console.log(res.data)

                    const archetypeNames = [];

                    for (let i = 0; i < res.data.length; i++) {

                        archetypeNames.push(res.data[i].archetype_name);
                    }

                    this.store.archetypes = archetypeNames;
                    console.log(this.store.archetypes)
                })
                .catch(error => {
                    console.error('Errore durante il recupero degli archetipi:', error);
                });
            },
        };

</script>

<template>
    <div class="container">

        <select name="archetype" id="archetype" @change="applyFilter">
            <option value="" selected disabled hidden>--Seleziona un'opzione--</option>
            <option v-for="archetype in store.archetypes" :value="archetype">{{ archetype }}</option>
        </select>
        
    </div>

</template>

<style lang="scss" scoped>

    .container {
        padding-bottom: 1em;

        select {
            padding: 8px 12px;
        }
    }

</style>