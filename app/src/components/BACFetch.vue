<template>
  <div class="card">
    <!--probably need to change-->
    <div v-for="center in centers" :key="facility_name">
      <!--will figure this out later-->
      <h2>{{ facility_name }}</h2>
      <h3>{{ id }}</h3>
      <h3>{{ zip_code }}</h3>
      <h3>{{ street_address }}</h3>
    </div>
    <h1>Working?</h1>
    <!--just a test-->
  </div>
</template>

<script setup>
//this script is a mess. props will probably be moved to another vue file
//fetch here instead without route.params.id? need to go to vue notes for reference
import { ref, onMounted } from "vue";
import { useRoute } from "vue-router";
const route = useRoute();
const centers = ref("");
import { computed } from "vue";
/* const props = defineProps({
  //does it need to be a const variable?
  facility_name: String, //could be Object or String
  id: Number, //will probably change
  zip_code: Number,
  street_address: String,
}); */
async function getCenters() {
  let res = await fetch(
    `https://data.cityofnewyork.us/resource/9d9t-bmk7.json`
  );
  let centersData = await res.json();
  let centersResult = centersData.results;
  return centersResult; //no console.log?
}
getCenters();
</script>

<style lang="css" scoped>
.card {
  border: 8px solid silver;
  align-items: center;
  position: relative;
}
h2 {
  text-decoration: underline;
  font-weight: bold;
}
</style>
