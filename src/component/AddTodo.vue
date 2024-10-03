<template>
   <input type="text" class="form-control add-todo" placeholder="Add todo" v-model="title" @keyup.enter="saveTodo(title)">
</template>

<script>
import EventBus from "../EventBus";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },

  methods: {
    saveTodo(title) {
      if (title === "") return;
      EventBus.$emit("add-todo", {
        title,
        id: Date.now().toString(),
        completed: false,
      });
      this.title = "";
    },
  },
};
</script>
