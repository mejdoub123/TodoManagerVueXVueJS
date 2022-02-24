<template>
  <div class="todos">
    <div
      @dblclick="onDblClick(todo)"
      v-for="todo in allTodos"
      :key="todo.id"
      class="todo-c-f"
      :class="{ 'todo-c-t': todo.completed }"
    >
      <div class="icon">
        <i @click="deleteTodo(todo.id)" class="fa-solid fa-xmark"></i>
      </div>
      <h4>{{ todo.title }}</h4>
    </div>
  </div>
</template>
<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "TodosComponent",
  methods: {
    ...mapActions(["fetchTodos", "deleteTodo", "updateTodo"]),
    onDblClick(todo) {
      const updTodo = {
        id: todo.id,
        title: todo.title,
        completed: !todo.completed,
      };
      this.updateTodo(updTodo);
    },
  },
  computed: mapGetters(["allTodos"]),
  created() {
    this.fetchTodos();
  },
};
</script>

<style scoped>
.todos {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 1rem;
  width: 80%;
  align-self: center;
}
.todo-c-f {
  border: 1px solid #d8d8d8;
  background-color: #ffffff;
  padding: 0.8rem 0.5rem;

  border-radius: 6px;
  text-align: center;
  position: relative;
  cursor: pointer;
}
.todo-c-t {
  border: 1px solid #d8d8d8;
  background-color: #206bc4;
  padding: 0.8rem 0.5rem;

  border-radius: 6px;
  text-align: center;
  position: relative;
  cursor: pointer;
}

.todo-c-t h4 {
  color: #ffffff;
}
.icon {
  display: flex;
  flex-direction: row;
  padding: 0px 0px 20px 5px;
}

.fa-xmark {
  padding: 4px 7px;
  background-color: #206bc4;
  border-radius: 4px;
  color: #ffffff;
  cursor: pointer;
}

.fa-xmark:hover {
  background-color: #0f5dbd;
}
</style>
