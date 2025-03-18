<template>
  <div></div>
</template>

<script setup>
import BACFetch from "@/components/BACFetch.vue";
const props = defineProps({
  //does it need to be a const variable?
  facility_name: String, //could be Object or String
  id: Number, //will probably change
  zip_code: Number,
  street_address: String,
});
</script>

<style lang="css" scoped></style>

<style scoped></style>
