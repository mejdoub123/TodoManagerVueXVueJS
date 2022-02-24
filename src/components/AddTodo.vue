<template>
  <div class="form-container">
    <h3>Add Todo</h3>
    <form @submit="onSubmit">
      <input type="text" v-model="title" placeholder="Add Todo..." />
      <input type="submit" value="Submit" />
    </form>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  name: "AddTodoComponent",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    ...mapActions(["addTodo"]),
    async onSubmit(e) {
      e.preventDefault();
      if (!this.title) {
        alert("Please enter a Todo...");
      } else {
        await this.addTodo(this.title);
      }
    },
  },
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Ubuntu:wght@300&display=swap");
.form-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #ffffff;
  border: 1px solid #b3b2b2;

  border-radius: 6px;
  margin-bottom: 2rem;
}
form {
  display: flex;

  margin: 15px 10px;
}
input[type="text"] {
  font-family: "Ubuntu", sans-serif;
  flex: 10;
  outline: none;
  border: 1px solid #d8d8d8;
  padding: 8px 12px;
  border-radius: 6px;
  margin: 8px 8px;
}
input[type="submit"] {
  flex: 2;
  font-family: "Ubuntu", sans-serif;
  outline: none;
  align-self: center;
  border: none;
  color: #ffffff;
  padding: 6px 8px;
  width: 40%;
  background-color: #206bc4;
  border-radius: 4px;
  margin: 8px;
  font-weight: 600;
  cursor: pointer;
}
input[type="submit"]:hover {
  background-color: #0f5dbd;
}
h3 {
  font-family: "Ubuntu", sans-serif;
  align-self: center;
  color: rgb(30, 74, 128);
}
</style>
