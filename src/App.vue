<template>
  <div class="container">
    <Header
      :showTodoField="showTodoField"
      @toggle-add-todo="toggleAddTodo"
      title="Todo List"
    />

    <div v-show="showTodoField">
      <AddTodo @add-todo="addTodo" />
    </div>
    <Todos
      @toggle-reminder="toggleReminder"
      @delete-todo="deleteTodo"
      :todos="todos"
    />
  </div>
</template>

<script>
import Header from "./components/Header";
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "App",
  components: {
    Header,
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [],
      showTodoField: false
    };
  },
  methods: {
    deleteTodo(id) {
      if (confirm("Are you sure?")) {
        this.todos = this.todos.filter(todo => todo.id !== id);
      }
    },
    toggleReminder(id) {
      this.todos = this.todos.map(todo =>
        todo.id === id ? { ...todo, reminder: !todo.reminder } : todo
      );
    },
    addTodo(todo) {
      this.todos = [...this.todos, todo];
    },
    toggleAddTodo() {
      this.showTodoField = !this.showTodoField;
    }
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
