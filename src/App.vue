<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <Header></Header>
      <List :todos="todos"></List>
      <div class="todo-footer">
        <Footer :getValue="getValue"></Footer>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import List from "@/components/List.vue";
import Footer from "@/components/Footer.vue";
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "",
  data() {
    return {
      todos: [
        { id: 1, content: "抽烟", isOver: false },
        { id: 2, content: "喝酒", isOver: true },
        { id: 3, content: "烧烤", isOver: false },
      ],
    };
  },
  components: {
    Header,
    List,

    Footer,
  },
  computed: {
    getValue: {
      get() {
        return this.todos.filter(() => {
          return true;
        });
      },
    },
  },
};
</script>

<style scoped>
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
