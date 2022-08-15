<template>
  <div class="col-5" style="max-height: 90vh; overflow: scroll">
    <div @click="$emit('show-details', country.id)" class="list-group" v-for="country in countries" :key="country.id">
      <router-link
        class="list-group-item list-group-item-action"
        :to="`/list/${country.alpha3Code}`"
      >
        <img
          :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
          alt=""
        />
        <p>{{ country.name.common }}</p>
      </router-link>
    </div>
    <div class="col-7">

      <router-view />
    </div>
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
