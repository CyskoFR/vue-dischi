<template>
    <header>
        <div class="container-fluid">
            <img class="logo" src="../assets/img/spotify-logo.png" alt="spotify-logo.png">
        </div>
    </header>
</template>

<script>

export default {

    name: 'HeaderComponent',

}

</script>

<style lang="scss" scoped>

header {
    padding: 10px;
    background-color: var(--primary-color);

    img {
        height: 40px;
    }

}

</style>