<template>
<div>
  <NavBar/>
  <div class="container">
    <div class="row">
      
      <CountriesList/>
      
      <CountryDetails/>
    </div>
  </div>
  
</div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
import CountriesList from "../components/CountriesList.vue";
import CountryDetails from "../components/CountryDetails.vue";
import countries from "../../public/countries.json"
export default {
    name: "HomeView",
  components: { NavBar, CountriesList, CountryDetails, countries },

  
  

}
</script>

<style>

</style>