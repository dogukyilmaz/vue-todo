<template>
  <div class="list">
    <ul>
      <li v-for="user in users" :key="user.name">{{ user.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [{ name: "dou" }, { name: "khan" }]
    };
  }
};
</script>

<style scoped>
.list {
  flex: 1;
  justify-content: center;
  align-items: center;
}
li {
  list-style-type: none;
}
</style>
