<template>
  <NavBar />
  <div class="container">
    <h1 class="text-center my-4 ">Country List</h1>
    <div v-if="this.countries" class="row">
      <div class="col-4" style="max-height: 90vh; overflow: scroll">
        <ul class="list-group">
          <router-link
            :to="`/list/${country.alpha3Code}`"
            v-for="(country, index) in countries"
            :key="index"
            class="list-group-item list-group-item-action list-unstyled"
          >
            <li>
              <img
                :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
                alt=""
              />
              <p>{{ country.name.common }}</p>
            </li>
          </router-link>
        </ul>
      </div>
      <div class="col-8">
          <router-view />
      </div>
    </div>
  </div>

 
</template>

<script>

import NavBar from "../components/NavBar.vue";
export default {
  name: "CountriesList",
  components: { NavBar },

  data() {
    return {
      countries: null,
    };
  },

  methods: {
    async fetchCountries() {
      const response = await fetch(
        "http://ih-countries-api.herokuapp.com/countries"
      );
      const finalResponse = await response.json();
      this.countries = finalResponse;
      console.log(finalResponse);

      this.countries = finalResponse.sort((a, b) => {
        return a.name.common.localeCompare(b.name.common);
      });
    },
  },
  //usamos el created-hook [created()] para hacer llamada inicial a base de datos y traernos esa info antes de que se pinte algo en el UI
  created() {
    this.fetchCountries();
  },
};
</script>

<style></style>
