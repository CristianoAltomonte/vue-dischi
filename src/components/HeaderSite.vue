<template>
    <div>
        <div class="contenitore-header">
            <img src="./img/svg-spotify.svg" alt="image" class="filter-green">
        </div>
    </div>
</template>

<script>

    export default {

        name: "HeaderSite",
    }

</script>

<style lang="scss" scoped>

.contenitore-header{
    background-color: rgba(42, 58, 71, 1);
    padding: 5px;
}

img{
    width: 8%;
}

.filter-green{
    filter: invert(65%) sepia(30%) saturate(7475%) hue-rotate(106deg) brightness(103%) contrast(105%);
    }

</style>