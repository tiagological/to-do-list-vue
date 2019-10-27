<template>
  <div class="container">
    <span>Add something new:</span>
    <input type="text" />
  </div>
</template>

<script>
export default {
  name: "Input"
};
</script>

<style scoped>
.container {
  align-self: stretch;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 2rem 0;
}

span {
  font-size: 2rem;
}

input {
  margin: 1rem 0;
  width: 40%;
  height: 2.5rem;
  text-align: center;
  font-size: 2rem;
  border-radius: 10px;
  border: 1px solid turquoise;
}

input:focus {
  outline: none;
  border-radius: 10px;
  border: 2px solid skyblue;
}

@media only screen and (min-width: 768px) {
  input {
    margin: 2rem;
  }
}
</style>
