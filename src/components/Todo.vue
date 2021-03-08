<template>
  <div class="todo">
    <h4>{{ todo.content }}</h4>
    <small>{{ todo.date }}</small>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: {
    todo: Object
  }
};
</script>

<style>
.todo h4 {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: 500;
}

.todo {
  background: rgb(251, 244, 244);
  margin: 5px;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
}

.todo.reminder {
  border-left: 6px solid greenyellow;
}
</style>
