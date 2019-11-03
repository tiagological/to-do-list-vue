<template>
  <div class="title">{{ title }}</div>
</template>

<script>
export default {
  name: "Title",
  props: {
    title: String
  }
};
</script>

<style scoped>
.title {
  color: #fff;
  text-shadow: 0 0 3px #000;
  margin-top: 2rem;
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
}

@media only screen and (min-width: 1024px) {
  .title {
    font-size: 3rem;
  }
}
</style>