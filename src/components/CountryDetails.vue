<template>
<div class="mx-auto pb-2" style="width: 200px;" v-if="countryIn">
    <img class="imagen"
      :src="`https://flagpedia.net/data/flags/icon/72x54/${alpha2Code.toLowerCase()}.png`"
      alt=""
    />
    <h1>{{ countryIn.name.common }}</h1>
    <div class="table">
      <thead></thead>
      <tbody>
        <tr>
          <td style="width: 30%">Capital</td>
          <td>{{ countryIn.capital[0] }}</td>
        </tr>
        <tr>
          <td>Area</td>
          <td>{{ countryIn.area }}km <sup>2</sup></td>
        </tr>
        <tr>
          <td>borders</td>
          <td>
            <ul v-for="(border, index) in countryIn.borders" :key="index">
              <li>
                <router-link :to="`/list/${border}`">{{ border }}</router-link>
              </li>
            </ul>
          </td>
        </tr>
      </tbody>
    </div>
    </div>
</template>

<script>
export default {
  name: "CountryDetails",

  data() {
    return {
      name: "",
      capital: "",
      alpha3Code: "",
      area: "",
      borders: [],
      alpha2Code: "",
     countryIn:{},
      
    };
  },
  methods: {
    async byAlphaCode() {
      this.alpha3Code = this.$route.params.alpha3Code;
      const response = await fetch(
        `http://ih-countries-api.herokuapp.com/countries/${this.alpha3Code}`
      );
      const finalResponse = await response.json();

      console.log(finalResponse);

      this.name = finalResponse.name.common;
      this.capital = finalResponse.capital[0];
      this.area = finalResponse.area;
      this.borders = finalResponse.borders;
      this.alpha2Code = finalResponse.alpha2Code;
      this.countryIn = finalResponse;
    },
  },
  created() {
    this.byAlphaCode();
  },

  computed: {
    countryCode() {
      return this.$route.params.alpha3Code;
    },
  },

  watch: {
    countryCode(newCountryCode) {
      this.byAlphaCode();
    },
  }
};
</script>

<style scoped>
.imagen{
  width: 150px;
  margin-top: 3rem;
}
</style>
