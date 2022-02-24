<template>
  <div class="home">
    <AddTodo />
    <FilterTodos />
    <Todos />
  </div>
</template>

<script>
// @ is an alias to /src
import Todos from "@/components/Todos.vue";
import AddTodo from "@/components/AddTodo.vue";
import FilterTodos from "@/components/FilterTodos.vue";

export default {
  name: "HomeView",
  components: {
    Todos,
    AddTodo,
    FilterTodos,
  },
};
</script>
<style scoped>
.home {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px 0px;
}
</style>
