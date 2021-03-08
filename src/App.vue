<template>
  <div class="container">
    <Header title="Todo List" />
    <Todos :todos="todos" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    Header,
    Todos
  },
  data() {
    return {
      todos: []
    };
  },
  created() {
    this.todos = [
      {
        id: 1,
        content: "Somethin about hospital.",
        date: "01-02-2021",
        reminder: true
      },
      {
        id: 2,
        content: "Lorem ipsum dolor.",
        date: "21-05-2021",
        reminder: false
      },
      {
        id: 3,
        content: "Met abet about etwq.",
        date: "06-02-2021",
        reminder: false
      }
    ];
  }
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 5px 10px;
  margin: 2px;
  border-radius: 8px;
  cursor: pointer;
  text-decoration: none;
  font-size: 14px;
  font-family: inherit;
  transition: all ease 100ms;
}
.btn:hover {
  opacity: 0.8;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.95);
}
/* .btn-block {
  display: block;
  width: 100%;
} */
</style>
