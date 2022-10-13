<template>
    <ul>
        <li v-for="countrie in countries">
            <router-link :to="{name: 'details', params:{code: countrie.alpha3Code} }">{{countrie.name.common}}</router-link>
        </li>
    </ul>

</template>

<script setup>
const props = defineProps({countries: Object})
</script>

<style scoped>
ul{
    border-right: dotted 2px;
    width: fit-content;
}
</style>