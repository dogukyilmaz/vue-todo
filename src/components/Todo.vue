<template>
  <div
    @dblclick="$emit('toggle-reminder', todo.id)"
    :class="[todo.reminder ? 'reminder' : '', 'todo']"
  >
    <h4>
      {{ todo.content }}
      <i @click="$emit('delete-todo', todo.id)" class="fas fa-times"></i>
    </h4>
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

i {
  color: rgb(88, 13, 73);
}

.todo {
  background: rgb(251, 244, 244);
  margin: 5px;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
}

.todo.reminder {
  border-left: 6px solid rgb(88, 13, 73);
}
</style>
