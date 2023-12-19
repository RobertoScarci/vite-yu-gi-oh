<script>
    export default {
    name: "AppSearch",
    data() {
        return {
            selectedArchetype: ""
        }
    },
    props: {
        archetypeList: {
            type: Object,
            required: true
        }
    },
    }
</script>

<template>
    <div class="container mb-3">
        <div class="row">
            <div class="col-2">
                <select class="form-select" aria-label="Default select example" @click="$emit('search',selectedArchetype)" v-model="selectedArchetype">
                    <option v-for="archetype in archetypeList" :value="archetype">{{ archetype }}</option>
                </select>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>

select{
    margin-left: 4rem;
    margin-top: 1rem;
}

</style>