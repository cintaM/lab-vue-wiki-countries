<template>
<div class="app">
  <NavBar />

  <div className="container">
    <div className="row">
      <CountriesList  />
      <CountryDetails />
      
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

  computed: {

    countries() {
        return data.map((country) => {
            return country
        })
    }
  }
  

}
</script>

<style>

</style>