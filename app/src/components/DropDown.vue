<!--drop down menu here-->
<template>
  <div class="dropdown-menu">
    <!--is this even how to make a drop down menu?-->
    <button onclick="dropDown()" class="dropbtn">Dropdown</button>
    <!--myFunction() subject to change-->
    <div class="dropdown-content">
      <a href="#">State</a>
      <a href="#">City</a>
      <a href="#">Borough</a>
    </div>
  </div>
</template>

<script setup></script>

<style lang="css" scoped>
.dropbtn {
  box-shadow: 8px 8px gray;
}
.dropdown-content {
  position: fixed;
}
</style>

<style scoped></style>
