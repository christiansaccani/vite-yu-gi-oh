<script>

export default {

    name: 'CardSearch',

    data() {
        return {
            searchText: ''
        };
    },
    methods: {
        search() {
            this.$emit('search', this.searchText);
        }
    }
};

</script>

<template>
    <div class="container">

        <div id="search-bar">
            <input type="search" name="searchText" v-model="searchText" placeholder="Cerca">
            <button @click="search" class="btn">Cerca</button>
        </div>
        
    </div>

</template>

<style lang="scss" scoped>
.container {
    padding: 0;
}

#search-bar {
    display: flex;
    gap: 12px;

    margin-bottom: 1em;

    input {
        padding: 6px 8px;
    }

    button {
        padding: 8px 12px;
    }
}


</style>