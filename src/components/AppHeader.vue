<script>
export default {

    name: 'AppHeader',

}
</script>

<!-- ---------------------------------------------------------------------------------- -->

<template>

    <header>
        <div>
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg/640px-Yu-Gi-Oh%21_%28Logo%29.jpg" alt="">
            <h1>Yu-Gi-Oh Api</h1>
        </div>
    </header>

</template>

<!-- ---------------------------------------------------------------------------------- -->

<style lang="scss">

header {
    div {
        display: flex;
        align-items: center;
        gap: 1em;

        padding: .5em;
        background-color: white;

        img {
            max-height: 50px;
        }
    }
}

</style>
