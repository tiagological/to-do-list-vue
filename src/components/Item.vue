<template>
  <div class="item-container">
    <div class="inner-container">
      <span>{{item.text}}</span>

      <button class="del-btn" v-on:click="$emit('delete-todo', item.id)">
        <font-awesome-icon icon="minus" class="del-icon" />
      </button>
    </div>
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
.item-container {
  border-top: 1px solid rgb(0, 0, 0, 0.3);
  border-radius: 5px;
  margin-bottom: 1rem;
  background-color: #fff;
  width: 100%;
}

@media only screen and (min-width: 1024px) {
  .item-container {
    width: 90%;
  }
}

.inner-container {
  width: 100%;
  padding: 0.5rem 1rem;
  display: flex;
  flex-direction: row;
  align-items: center;
}

span {
  font-size: 1.25rem;
  word-break: break-all;
  hyphens: auto;
}

.del-btn {
  color: red;
  font-weight: bold;
  height: 3rem;
  width: 3rem;
  margin-left: auto;
  flex-shrink: 0;
  background-color: transparent;
  border: transparent;
  border-radius: 50%;
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