<template>
  <div>
    <h1>hola</h1>
      <!-- <img :src="image" alt="country flag" style="width: 300px" />
      <h1>{{ name }}</h1>
      <div class="table">
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
    </div> -->
  </div>
</template>

<script>
export default {
  name: "CountryDetails",

  data(){
    return {
      image: "",
      name: "",
      border: [],
      area: "",
      capital: ""
    }
  }
};
</script>

<style></style>
