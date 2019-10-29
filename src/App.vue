<template>
  <div id="app">
    <VueLogo />
    <Title title="Vue To Do List" />
    <AddToDo v-on:add-todo="addToDo" />
    <List :list="list" v-on:delete-todo="deleteTodo" />
    <h1 v-if="list.length === 0">Nothing to do!</h1>
  </div>
</template>


<script>
import VueLogo from "./components/VueLogo";
import Title from "./components/Title";
import AddToDo from "./components/AddToDo";
import List from "./components/List";

export default {
  name: "app",
  components: {
    VueLogo,
    Title,
    AddToDo,
    List
  },
  data() {
    return {
      list: []
    };
  },
  methods: {
    deleteTodo: function(id) {
      this.list = this.list.filter(item => item.id !== id);
    },
    addToDo(newToDo) {
      this.list = [...this.list, newToDo];
    }
  }
};
</script>

<style>
html,
body {
  height: 100%;
  width: 100%;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  width: 100%;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: inherit;
}

h1 {
  color: #35495e;
}
</style>
