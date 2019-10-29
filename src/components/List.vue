<template>
  <div class="list-container">
    <transition-group name="list" tag="p">
      <Item
        v-for="item in list"
        v-bind:key="item.id"
        v-bind:item="item"
        v-on:delete-todo="$emit('delete-todo', item.id)"
        class="list-item"
      />
    </transition-group>
  </div>
</template>

<script>
import Item from "./Item";

export default {
  name: "List",
  components: {
    Item
  },
  props: {
    list: Array
  }
};
</script>

<style scoped>
div {
  list-style-type: none;
  text-align: center;
  width: 100%;
}

.list-enter-active,
.list-leave-active {
  transition: all 400ms;
}
.list-enter,
.list-leave-to {
  opacity: 0;
  transform: translateX(100px);
}
</style>