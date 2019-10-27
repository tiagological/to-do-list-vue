<template>
  <img src="../assets/logo.png" alt="Vue logo" />
</template>

<script>
export default {
  name: "VueLogo"
};
</script>

<style scoped>
img {
  height: 5rem;
  width: auto;
  margin: 2rem 0;
}

@media only screen and (min-width: 1024px) {
  img {
    height: 7.5rem;
    width: auto;
  }
}
</style>