<template>
  <div class="pink-5">
    <q-form @submit.prevent="onsubmit" @reset="onReset" class="q-gutter-md">
      <div>
        <q-input
          v-model="todo"
          type="text"
          :label="$t('input your reminding')"
        />
      </div>
      <div>
        <q-btn :label="$t('addBtn')" type="submit" color="pink-3" />
      </div>
    </q-form>
  </div>
</template>

<script>
import { useTodoStore } from "../stores/todoList";
const langoptions = [
  { value: "en-US", label: "English" },
  { value: "th", label: "Thai" },
];
export default {
  name: "TodoForm",
  data() {
    return {
      todo: "",
      store: useTodoStore(),
      langoptions,
      lang: "",
    };
  },
  methods: {
    onsubmit() {
      console.log("s:" + this.todo);
      if (this.todo.lenght == 0) return;
      this.store.addToDo(this.todo);
      this.todo = "";
    },
    onreset() {
      this.todo = "";
    },
    watch: {
      lang() {
        this.$in18n.locale = this.lang.value;
        import(`src/i18n/${this.lang.value}`).then((language) => {
          this.$q.lang.set(language.default);
        });
      },
    },
  },
};
</script>

<style></style>
