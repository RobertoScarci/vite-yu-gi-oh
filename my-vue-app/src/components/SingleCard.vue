<script>
    export default {
    name: "SingleCard",
    props: {
        card: {
            type: Object,
            required: true
        }
    }
    }
</script>

<template>
    <div class="card col-12 col-md-4 col-lg-2 mb-4 me-3">
        <img :src="card.card_images[0].image_url" class="img-fluid " :alt=" card.name + '\'s card'">
        <div class="card-body">
            <h6 class="card-title text-white"> {{ card.name }} </h6>
            <p class="card-text"> {{ card.archetype }} </p>
        </div>
    </div>
</template>

<style lang="scss" scoped>

div{
    background-color: #D48F37;
}
</style>