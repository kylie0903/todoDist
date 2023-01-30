<template>
  <div>
    <input type="date" v-model="todoDate" />
    <input type="text" v-model="todoItem" />
    <button @click="addTodo">추가</button>
  </div>
  <ul>
    <li
      v-for="(todo, index) in todolist"
      :key="todo"
      v-bind:class="{ completed: todo.complete }"
    >
      {{ index + 1 }}
      {{ todo.dates }} / {{ todo.item }} / {{ todo.complete }}
      <span @click="complete(todo, index)">표시</span> |
      <span @click="removeTodo(todo, index)">삭제</span>
    </li>
  </ul>
  <div></div>
</template>
<script>
export default {
  data: function () {
    return {
      todoDate: "",
      todoItem: "",
      todolist: [],
    };
  },
  methods: {
    addTodo: function () {
      console.log(this.todoItem);
      if (this.todoItem != "") {
        var obj = {
          dates: this.todoDate,
          item: this.todoItem,
          complete: false,
        };
        localStorage.setItem(this.todoItem, JSON.stringify(obj));
        this.todolist.push(obj);
        this.todoDate = "";
      }
    },
    removeTodo: function (todo, index) {
      localStorage.removeItem(todo.item);
      this.todolist.splice(index, 1);
      console.log(todo);
    },
    complete: function (todo, index) {
      todo.complete = !todo.complete;
      localStorage.removeItem(todo.item);
      localStorage.setItem(todo.complete, JSON.stringify(todo));
      console.log(todo);
    },
  },
  created: function () {
    if (localStorage.length > 0) {
      for (var i = 2; i < localStorage.length; i++) {
        if (localStorage.key(i) !== "loglevel:webpack-dev-server") {
          this.todolist.push(
            JSON.parse(localStorage.getItem(localStorage.key(i)))
          );
        }
      }
    }
  },
};
</script>
<style scoped>
.completed {
  background-color: yellow;
}
</style>