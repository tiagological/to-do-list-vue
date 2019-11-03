<template>
  <div class="container">
    <form v-on:submit="addToDo">
      <input
        placeholder="Type something..."
        type="text"
        name="todo"
        v-model="text"
        class="input-text-field"
      />
      <button type="submit" class="add-btn">
        <font-awesome-icon icon="plus" class="add-icon" />
      </button>
    </form>
  </div>
</template>

<script>
import uuid from "uuid";
export default {
  name: "AddToDo",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    addToDo(e) {
      e.preventDefault();
      if (this.text.length === 0) {
        return;
      }

      const newToDo = {
        id: uuid.v4(),
        text: this.text,
        completed: false
      };

      this.$emit("add-todo", newToDo);
      this.text = "";
    }
  }
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
  padding: 0 1rem;
}

form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.input-text-field {
  margin: 1rem 0;
  width: 100%;
  height: 4rem;
  padding: 1rem;
  text-align: center;
  font-size: 1.5rem;
  border-radius: 5px;
  border: none;
  color: #2f2fa2;
}

.input-text-field:focus {
  outline: none;
  border-radius: 5px;
  border: 2px solid #2f2fa2;
}

.add-btn {
  font-weight: bold;
  border-style: none;
  border-radius: 50%;
  background-color: transparent;
  color: #2f2fa2;
  height: 3rem;
  width: 3rem;
  transition: all 200ms;
}

.add-btn:hover {
  cursor: pointer;
  background-color: #fff;
}

.add-icon {
  height: 2rem;
  width: auto;
}
</style>
