<template>
  <div class="container">
    <a href="https://www.tsmarques.com">
      <span>By TSMarques</span>
    </a>
  </div>
</template>

<script>
export default {
  name: "Footer"
};
</script>
  
<style scoped>
.container {
  width: 100%;
  margin-top: auto;
  margin-bottom: 2rem;
  display: flex;
  justify-content: center;
  font-size: 1.25rem;
}

a {
  text-decoration: none;
}

a:hover {
  cursor: pointer;
}

span {
  color: #fff;
}
</style>