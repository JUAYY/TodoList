<template>
  <div class="q-pt-md pink-5" v-if="store.todoList.length > 0">
    <!-- list -->
    <div class="q-pa-md" style="max-width: 350px">
      <q-list bordered separator>
        <q-item
          clickable
          v-ripple
          v-for="todo in store.todoList"
          :key="todo.id"
        >
          <q-item-section :class="{ completeClass: todo.completed }">{{
            todo.item
          }}</q-item-section>
          <q-item-section avatar
            ><q-icon
              name="check"
              color="pink-5"
              @click="store.toggleCompleted(todo.id)"
          /></q-item-section>
          <q-item-section avatar
            ><q-icon
              name="delete"
              color="pink-5"
              @click="store.deleteToDo(todo.id)"
          /></q-item-section>
        </q-item>
      </q-list>
    </div>
  </div>
  <!-- list -->
  <div class="q-pt-md" v-else>No Data</div>
</template>

<script>
import { useTodoStore } from "../stores/todoList";
export default {
  name: "TodoList",
  data() {
    return { store: useTodoStore() };
  },
};
</script>

<style>
.completeClass {
  text-decoration: line-through;
}
</style>
