<template>
  <div>
    <NavBar />
    <router-view :key="$route.fullPath" />
  </div>
</template>

<script>
import NavBar from "./components/NavBar";

export default {
  components: { NavBar }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Amatic+SC&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
