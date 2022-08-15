<template>
  <div class="col-5" style="max-height: 90vh; overflow: scroll">
    <div class="list-group" v-for="country in countries" :key="country.id">
      <router-link
        class="list-group-item list-group-item-action"
        :to="`/list/${country.alpha3Code}`"
      >
        <img :src="country.image" />
        <p>{{ country.name.common }}</p>
      </router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
import countries from "../../public/countries.json";

export default {
  name: "CountriesList",
  data() {
    return {
      countries: countries,
    };
  },
};
</script>

<style></style>
