<template>
  <div>
    <p>{{item.text}}</p>
    <button class="del-btn" v-on:click="$emit('delete-todo', item.id)">
      <font-awesome-icon icon="minus" class="del-icon" />
    </button>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: {
    item: Object
  }
};
</script>

<style scoped>
div {
  margin: 1rem 0;
  border-radius: 5px;
  padding: 0.5rem 1rem;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  box-shadow: 0 0 3px #35495e;
}

p {
  font-size: 1.25rem;
}

.del-btn {
  color: red;
  font-weight: bold;
  height: 3rem;
  width: 3rem;
  background-color: transparent;
  border: transparent;
  border-radius: 50%;
  transition: all 200ms;
}

.del-btn:hover {
  cursor: pointer;
  background-color: #fff1f3;
}

.del-icon {
  height: 2rem;
  width: auto;
}
</style>