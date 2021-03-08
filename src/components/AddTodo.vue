<template>
  <form @submit="handleSubmit" class="add-form">
    <div class="form-control">
      <label>Todo</label>
      <input
        type="text"
        v-model="content"
        name="content"
        placeholder="Add Todo"
      />
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input type="text" v-model="date" name="date" placeholder="Date & Time" />
    </div>
    <div class="form-control form-control-check">
      <label>Reminder</label>
      <input type="checkbox" v-model="reminder" name="reminder" />
    </div>

    <input type="submit" value="Save" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      content: "",
      date: "",
      reminder: false
    };
  },
  methods: {
    handleSubmit(e) {
      e.preventDefault();
      if (!this.content) {
        alert("Fill content");
        return;
      }

      const newTodo = {
        id: Math.floor(Math.random() * 10000),
        content: this.content,
        date: this.date,
        reminder: this.reminder
      };
      this.clearForm();
      this.$emit("add-todo", newTodo);
    },
    clearForm() {
      (this.content = ""), (this.date = ""), (this.reminder = false);
    }
  }
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: start;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>
