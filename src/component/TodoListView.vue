<template>
    <ul id="sortable" class="list-unstyled" >
        <li class="ui-state-default" v-for="todo in todos" :key="todo.id">
            <div class="checkbox">
                <label>
                    <input type="checkbox" value="" @click="finishedTodo(todo.id)" />
                   {{todo.title}}
                </label>
            </div>
        </li>
        
    </ul>
</template>

<script>
import EventBus from "../EventBus";
export default {
  name: "TodoListView",
  props: {
    todos: {
      type: Array,
      Required: true,
    },
  },
  methods: {
    finishedTodo(todId) {
      EventBus.$emit("completed-todo", { id: todId });
    },
  },
};
</script>
