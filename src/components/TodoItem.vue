<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{todo.title}}
      <button @click="$emit('del-todo', todo.id)" class="del">X</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"], // Accepting passed todo single as prop
  methods: {
    markComplete() {
      console.log(123);
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px dotted #cccccc;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: #ff0000;
  color: #ffffff;
  border-radius: 100px;
  border: none;
  padding: 5px 8px;
  cursor: pointer;
  float: right;
}
</style>
