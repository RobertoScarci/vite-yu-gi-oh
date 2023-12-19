<script>
    import SingleCard from './SingleCard.vue';

    export default {
        name: "ListCards",
        components: {
            SingleCard
        },
        props: {
            cardsList: {
                type: Object,
                required: true
            }
        }
    }
</script>

<template>
    <div class="container pt-4">
        <div class="row justify-content-center">
            <span class="text-white bg-dark mb-0 p-1 col-10">
                Found 39 cards
            </span>
            <SingleCard class="p-0" v-for="card in cardsList" :card="card"/>
        </div>
    </div>
</template>

<style lang="scss" scoped>

.container{
    text-align: center;
    text-transform: uppercase;
    font-size: 12px;
    background-color: white;
}

span{
    height: 40px;
    font-size: 20px;
}



</style>