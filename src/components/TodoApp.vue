<template>
  <div class="pink-5">
    <h6>TO DO LIST</h6>
    <TodoForm></TodoForm>
    <TodoList></TodoList>
  </div>
</template>

<script>
import TodoForm from "../components/TodoForm.vue";
import TodoList from "../components/TodoList.vue";
export default {
  name: "TodoApp",
  components: { TodoForm, TodoList },
};
</script>

<style></style>
