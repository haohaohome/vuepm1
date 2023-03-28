<template>
  <div>
    <li>
      <label>
        <input type="checkbox" v-model="checkedtodo" />
        <span>{{ todo.content }}</span>
      </label>
      <button class="btn btn-danger" style="display: none">删除</button>
    </li>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "",
  props: { todo: Object },
  computed: {
    checkedtodo: {
      get() {
        return this.todo.isOver;
      },
      set(value) {
        // eslint-disable-next-line vue/no-mutating-props
        this.todo.isOver = value;
      },
    },
  },
  methods: {},
};
</script>

<style scoped>
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
</style>
