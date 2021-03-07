<template>
  <header>
    <h1>{{ title }}</h1>
    <Button title="Add Todo" color="green" />
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "No name",
  props: {
    title: String
    // title: {
    //   type: String,
    //   default: "No name"
    // }
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
