<template>
  <div id="app">
    <VueLogo />
    <Title title="Vue To Do List" />
    <Input />
  </div>
</template>

<script>
import VueLogo from "./components/VueLogo";
import Title from "./components/Title";
import Input from "./components/Input";

export default {
  name: "app",
  components: {
    VueLogo,
    Title,
    Input
  }
};
</script>

<style>
html,
body {
  height: 100%;
  width: 100%;
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  width: 100%;
  padding: 3rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
