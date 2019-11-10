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
  margin-top: 2rem;
  font-size: 3rem;
  font-weight: bold;
  text-align: center;
}

@media only screen and (min-width: 1024px) {
  .title {
    font-size: 3rem;
  }
}
</style>