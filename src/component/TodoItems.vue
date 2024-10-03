<template>
    <div class="todo-footer">
        <strong>
            <span class="count-todos"></span>
        </strong>{{ todos.filter(todo => !todo.completed).length }} Items Left
    </div>
</template>

<script>
import { todos } from "../seed";

export default {
  name: "TodoItems",

  data() {
    return {
      todos: todos,
    };
  },
};
</script>
