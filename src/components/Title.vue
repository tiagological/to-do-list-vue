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
  color: #35495e;
}

@media only screen and (min-width: 1024px) {
  .title {
    font-size: 3rem;
  }
}
</style>