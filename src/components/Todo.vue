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

<style></style>
