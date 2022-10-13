<template>
    <div v-if="result.length > 0">
        <img :src="image" alt="">
        <h1>{{result[0].name.common}}</h1>
        <br>
        <div>Capital:  {{result[0].capital}}</div>
        <div>Area: {{result[0].area}}km2</div>
        <div>Borders: 
            <ul>
                <li v-for="border in result[0].borders">{{border.value}}</li>
            </ul>
            <br>
        </div>
    </div>

    {{route}}
</template>
<script setup>
import {onMounted,onUpdated, ref } from 'vue';
import {useRoute} from 'vue-router'
import CountriesList from '../assets/countries.json'
let result = ref([]);
let id = ref(0);
const route = useRoute();
let image = ''

id= route.params.code;
    result = CountriesList.filter(countrie =>{
        if(countrie.alpha3Code == id) 
        return countrie;
    });

    if(result.length>0)
        image = "https://flagpedia.net/data/flags/icon/72x54/"+result[0].alpha2Code+".png";

</script>
<style scoped>
</style>