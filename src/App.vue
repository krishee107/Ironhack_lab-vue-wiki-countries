<template>
<div class="app">
  <Navbar />
  <div class="section">
    <div class="container columns">
        <div class="column countries">
            <CountriesList :countries="countries" />
            <router-view/>
        </div>
        <div class="column details">
            <CountriesDetails/>
        </div>
    </div>
  </div>

</div>


</template>
  
<script setup>
import Navbar from './components/Navbar.vue';
import CountriesList from './views/CountriesList.vue';
import CountriesDetails from './views/CountriesDetails.vue';
import countries from './assets/countries.json'



   
</script>
  
<style scoped>
  
</style>
