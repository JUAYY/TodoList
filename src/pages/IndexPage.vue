<template>
  <q-page class="flex flex-center pink-5">
    <TodoApp> </TodoApp>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import TodoApp from "../components/TodoApp.vue";

export default defineComponent({
  name: "IndexPage",
  components: { TodoApp },
});
</script>
