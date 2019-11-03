<template>
  <div id="app">
    <header>
      <Title title="To Do List" />
      <AddToDo v-on:add-todo="addToDo" />
    </header>
    <List :list="list" v-on:delete-todo="deleteTodo" />
    <transition name="fade">
      <h2 v-if="list.length === 0" class="placeholder">Add something to your list</h2>
    </transition>
  </div>
</template>


<script>
import Title from "./components/Title";
import AddToDo from "./components/AddToDo";
import List from "./components/List";

export default {
  name: "app",
  components: {
    Title,
    AddToDo,
    List
  },
  data() {
    return {
      list: []
    };
  },
  created() {
    const storedList = JSON.parse(localStorage.getItem("list"));
    this.list = storedList || [];
  },
  methods: {
    deleteTodo: function(id) {
      this.list = this.list.filter(item => item.id !== id);
      localStorage.setItem("list", JSON.stringify(this.list));
    },
    addToDo(newToDo) {
      this.list = [...this.list, newToDo];
      localStorage.setItem("list", JSON.stringify(this.list));
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Muli&display=swap");

html,
body {
  height: 100%;
  width: 100%;
  font-family: "Muli", sans-serif;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#app {
  font-family: "Muli", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  width: 100%;
  background-color: #2f2fa2;
  overflow-y: auto;
  overflow-x: hidden;
  display: flex;
  flex-direction: column;
  align-items: center;
  box-sizing: inherit;
}

header {
  background-color: #f64c72;
  width: 100%;
  clip-path: polygon(0 0, 100% 0, 100% 75%, 50% 100%, 0% 75%);
  margin-bottom: 2rem;
}

.placeholder {
  color: #fff;
}

.fade-enter {
  opacity: 0;
  transform: translateY(100px);
}

.fade-leave-to {
  opacity: 0;
}

.fade-enter-active {
  transition-delay: 1s;
  transition-property: opacity, transform;
}

.fade-leave-active {
  transition: opacity 200ms;
}
</style>
