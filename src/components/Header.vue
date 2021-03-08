<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      @button-click="$emit('toggle-add-todo')"
      :title="showTodoField ? 'Close' : 'Add Todo'"
      :color="!showTodoField ? 'green' : 'rgb(88, 13, 73)'"
    />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "No name",
  props: {
    title: String,
    // title: {
    //   type: String,
    //   default: "No name"
    // }
    showTodoField: Boolean
  },
  components: {
    Button
  }
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}
</style>
