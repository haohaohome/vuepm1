<template>
  <div>
    <ul class="todo-main">
      <item
        v-for="(todo, index) in todos"
        :key="todo.id"
        :index="index"
        :todo="todo"
      ></item>
    </ul>
  </div>
</template>

<script>
import Item from "./Item.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "",
  components: {
    Item,
  },
  props: ["todos"],
};
</script>

<style scoped>
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>
