<template>
  <div>
    <h1>Working?</h1>
    <!--just a test-->
  </div>
</template>

<script setup>
//fetch here instead without route.params.id? need to go to vue notes for reference
import { red, onMounted } from "vue";
import { useRoute } from "vue-router";
const route = useRoute();
const centers = ref("");
import { computed } from "vue";
const props = defineProps({
  facility_name: String, //could be String instead of Object
  id: Number, //will probably change
  zip_code: Number,
  street_address: String,
});
async function getCenters() {
  let res = await fetch(
    `https://data.cityofnewyork.us/resource/9d9t-bmk7.json${route.params.id}` //route.params.id might not be needed here yet
  );
  let centersData = await res.json();
  let centersResult = centersData.results;
  console.log(centersResult);
}
getCenters();
</script>

<style lang="css" scoped></style>
