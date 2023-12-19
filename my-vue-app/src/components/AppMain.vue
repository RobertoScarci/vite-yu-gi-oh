<script>
    import Listcards from './ListCards.vue';
    import AppSearch from './AppSearch.vue';
    import axios from 'axios';

    export default {
        name: "AppMain",
        components: {
            Listcards,
            AppSearch
        },
        data() {
            return {
                cardsList: [],
                archetypeList : []
            }
        },
        methods: {
            getcardList(archetype) {
                axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php', {
                    params: {
                    num: 100,
                    offset: 0,
                    archetype : archetype
                    }
                })
                .then( response => {
                    console.log(response);
                    this.cardsList = response.data.data;
                })
                .catch(function (error) {
                    console.log(error);
                });
            },
            filterArchetype() {
                this.cardsList.forEach( card => !this.archetypeList.includes(card.archetype) ? this.archetypeList.push(card.archetype) : '' );
                return this.archetypeList;
            },
            selectArchetype(archetype) {
                this.getcardList(archetype);
            }
        },
        created() {
            this.getcardList()
        }
    }
</script>

<template>
    <AppSearch :archetypeList="filterArchetype(cardsList)" @search="selectArchetype"/>
    <Listcards :cardsList="cardsList"/>
</template>

<style lang="scss" scoped>

</style>