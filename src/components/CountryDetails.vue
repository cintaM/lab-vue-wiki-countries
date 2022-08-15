<template>
  <div>
    <div class="col-7" >
      <img :src="image" alt="country flag" style="width: 300px" />
      <h1>{{ name }}</h1>
      <table class="table">
        <thead></thead>
        <tbody>
          <tr>
            <td style="width: 30%">Capital</td>
            <td>{{ capital }}</td>
          </tr>
          <tr>
            <td>Area</td>
            <td>{{ area }} <sup>2</sup></td>
          </tr>
          <tr>
            <td>{{ border }}</td>
            <td>
              <ul>
                <li><a href="/AND">Andorra</a></li>
                <li><a href="/BEL">Belgium</a></li>
                <li><a href="/DEU">Germany</a></li>
                <li><a href="/ITA">Italy</a></li>
                <li><a href="/MCO">Monaco</a></li>
                <li><a href="/ESP">Spain</a></li>
                <li><a href="/CHE">Switzerland</a></li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "CountryDetails",

  props: {
    image: String,
    name: String,
    border: Array,
    area: String,
    capital: String,
  },
};
</script>

<style></style>
