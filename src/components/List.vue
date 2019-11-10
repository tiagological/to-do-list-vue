<template>
  <div class="list-container">
    <transition-group name="list" tag="div" class="transition-wrapper">
      <Item
        v-for="item in list"
        v-bind:key="item.id"
        v-bind:item="item"
        v-on:delete-todo="$emit('delete-todo', item.id)"
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
.list-container {
  text-align: left;
  width: 100%;
  margin-bottom: 3rem;
  padding: 0 1rem;
}

.transition-wrapper {
  width: 100%;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.list-enter,
.list-leave-to {
  opacity: 0;
  transform: translateY(100px);
}

.list-enter-active,
.list-leave-active {
  transition: all 500ms;
}

.list-leave-active {
  position: absolute;
  width: 100%;
}

@media only screen and (min-width: 1024px) {
  .list-leave-active {
    width: 90%;
  }
}

.list-move {
  transition: transform 500ms;
}
</style>