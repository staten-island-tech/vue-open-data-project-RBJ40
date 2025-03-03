<template>
  <div></div>
</template>

<script setup>
import { red, onMounted } from "vue";
import { useRoute } from "vue-router";
const route = useRoute();
const pokemon = ref("");
import { computed } from "vue";
const props = defineProps({
  facility_number: Object, //could be String instead of Object
  id: Number, //will probably change
});
async function getCenters() {
  let res = await fetch(
    `https://data.cityofnewyork.us/resource/9d9t-bmk7.json${route.params.id}` //route.params.id might not be needed here yet
  );
  let centersData = await res.json();
  let centersResult = centersData.results;
  return centersResult;
}
getCenters();
</script>

<style lang="css" scoped></style>
