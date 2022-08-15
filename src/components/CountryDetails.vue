<template>
  
    <div class="col-7">
    <img
          :src="`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`"
          alt=""
        />
    <h1>{{ country.name.common }}</h1>
    <div class="table">
      <thead></thead>
      <tbody>
        <tr>
          <td style="width: 30%">Capital</td>
          <td>{{ country.capital }}</td>
        </tr>
        <tr>
          <td>Area</td>
          <td>{{ country.area }}km <sup>2</sup></td>
        </tr>
        <tr>
          <td>borders</td>
          <td>
            <ul  v-for="border in country.borders" :key="border">
              <li><a href="/AND">{{border}}</a></li>
              
            </ul>
          </td>
        </tr>
      </tbody>
    </div>
  </div>
  
</template>

<script>
import countries from "../../public/countries.json";
export default {
  name: "CountryDetails",

  data() {
    return {
      countries: countries,
      details: this.$route.params.details,

      country: countries.filter((country1) => country1.alpha3Code === this.$route.params.details)[0]
    };
  },
};
</script>

<style></style>
